# Windwalker Joomla RAD Development Bundle

## Installation via Composer

``` bash
cd /to/your/joomla

composer create-project windwalker/rad-development-bundle libraries/windwalker-bundles/DevelopmentBundle 1.*
```

## Commands

``` bash
Windwalker Console - version: 2.1
------------------------------------------------------------

# system commands ...

  seed         The data seeder help you create fake data.
    import       Import seeders.
    clear        Clear seeders.

  sql          SQL sync & diff tools.
    backup       Backup sql.
    col          Column operation
    export       Export sql.
    import       Import a sql file.
    profile      Profiles.
    restore      Restore to pervious point.
    table        Model operation.
```

## SQL Sync

### Export & Import SQL Schema

``` bash
php bin/windwalker sql export

php bin/windwalker sql import
```

Scheam will export to `resources/sqlsync/default/schema.yml`

### Track Tables

Table track information stores in `resources/sqlsync/default/track.yml`

Default is:

``` yaml
table:
    '#__assets': all
    '#__associations': all
    '#__banner_clients': all
    '#__banner_tracks': all
    '#__banners': all
    '#__categories': all
    '#__contact_details': all
    '#__content': all
    '#__content_frontpage': all
    '#__content_rating': all
    '#__content_types': all
    '#__contentitem_tag_map': all
    '#__core_log_searches': all
    '#__extensions': all
    '#__finder_filters': cols
    '#__finder_links': cols
    '#__finder_links_terms0': cols
    '#__finder_links_terms1': cols
    '#__finder_links_terms2': cols
    '#__finder_links_terms3': cols
    '#__finder_links_terms4': cols
    '#__finder_links_terms5': cols
    '#__finder_links_terms6': cols
    '#__finder_links_terms7': cols
    '#__finder_links_terms8': cols
    '#__finder_links_terms9': cols
    '#__finder_links_termsa': cols
    '#__finder_links_termsb': cols
    '#__finder_links_termsc': cols
    '#__finder_links_termsd': cols
    '#__finder_links_termse': cols
    '#__finder_links_termsf': cols
    '#__finder_taxonomy': cols
    '#__finder_taxonomy_map': cols
    '#__finder_terms': cols
    '#__finder_terms_common': all
    '#__finder_tokens': cols
    '#__finder_tokens_aggregate': cols
    '#__finder_types': cols
    '#__languages': all
    '#__menu': all
    '#__menu_types': all
    '#__messages': all
    '#__messages_cfg': all
    '#__modules': all
    '#__modules_menu': all
    '#__newsfeeds': all
    '#__overrider': all
    '#__postinstall_messages': all
    '#__redirect_links': all
    '#__schemas': all
    '#__session': cols
    '#__tags': all
    '#__template_styles': all
    '#__ucm_base': all
    '#__ucm_content': all
    '#__ucm_history': all
    '#__update_sites': all
    '#__update_sites_extensions': all
    '#__updates': cols
    '#__user_keys': all
    '#__user_notes': all
    '#__user_profiles': all
    '#__user_usergroup_map': all
    '#__usergroups': all
    '#__users': all
    '#__utf8_conversion': all
    '#__viewlevels': all
```

There are 3 track rules:

- `all` - Track all data, always refresh data when import & export.
- `cols` - Only track table columns, do not refresh data.
- `none` - Ignore this table

> All table which not list in track.yml will be `none`.

## Sync Track Tables

If you installed a new component, there may be multiple tables added to ypur database, you can run:

``` bash 
php bin/windwalker sql table sync
```

To auto add all non-tracked table to `track.yml`

## Status

This command help you check table track information.

``` bash
php bin/windwalker sql status
```

![p-2016-04-05-006](https://cloud.githubusercontent.com/assets/1639206/14274758/d143e078-fb45-11e5-9e53-c5967f94a5a9.jpg)







