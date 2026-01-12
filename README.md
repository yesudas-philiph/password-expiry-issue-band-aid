# Password Expiry Band-Aid – Ubuntu Server 22.04 (Dirty Fix)

**Status:** Quick & Dirty Workaround  
**Last Updated:** January 2026  
**Applies to:** Ubuntu Server 22.04 LTS 

## The Problem

Ubuntu 22.04 server,  local `chage` password ageing settings (like `chage -M -1`) get **silently overwritten/reset** after reboot.

Typical symptoms:
- Service/test accounts get unexpected password expiry despite local override attempts

## Band-Aid Solution (Re-apply settings at every boot)

Add this to **root's crontab** (most reliable on Ubuntu 22.04):

added a cron at @reboot for setting chage -M -1 test 
