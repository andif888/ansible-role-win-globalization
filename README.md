ansible-role-win-globalization
=========

this role changes regional, language and timezone settings in windows.

Requirements
------------

changes to language settings requires that corresponding language packs are already installed.

Role Variables
--------------

```yaml
# Copies the current user's international settings
# (Windows Display language, Input language, Regional Format/locale, and Location/GeoID)
# to one or both of the following:
# Welcome screen and system accounts
# New user accounts
win_globalization_copy_to_system_and_user: true

# Geographical Locations
# https://docs.microsoft.com/en-us/windows/win32/intl/table-of-geographical-locations?redirectedfrom=MSDN
win_globalization_geo_id: 94

# HKLM:\SYSTEM\CurrentControlSet\Control\MUI\Settings
# PreferredUILanguages
win_globalization_system_mui: 'de-DE'

win_globalization_system_locale: 'de-DE'
win_globalization_system_timezone: 'W. Europe Standard Time'

win_globalization_user_locale: 'de-DE'

# Input Locales
# https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/default-input-locales-for-windows-language-packs
win_globalization_user_input: '0407:00000407'

```

Example Playbook
----------------

```yaml
---
- hosts: win10
  become: true
  gather_facts: true
  vars:

  roles:
    - ansible-role-win-globalization
```
