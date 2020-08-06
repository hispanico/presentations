---
title: Automation Journey

---

## Automation Journey

Follow along: http://robertdebock.nl/

<img src="https://api.qrserver.com/v1/create-qr-code/?size=350x350&data=http://robertdebock.nl/presentations/automation-journey/"/>

---

# Who am I

[![Octocat](images/octocat.png)](https://github.com/robertdebock) - Robert de Bock

---

## An automation tale

---

# What to automate

1. Make a list of job.
2. Rate job for "frequent" and "automation effort".
3. Decide.
4. CODE!

----

# List of jobs

Think of a few jobs that you'd like to automate.

----

## Suggestion of jobs

- Applying patches
- Disk expansions
- Install component x
- Update component x

----

# Rate jobs

1: not frequent, low effort
10: super frequent, high effort

----

# Rated jobs

|job           |frequency|automation effort|
|--------------|---------|-----------------|
|OS patches    |9        |3                |
|Disk expansion|3        |9                |
|Install X     |3        |4                |
|Update X      |2        |3                |

----

# Decide

OS patching: is occurs all the time and seems easy to automate.

In other words, if you don't need to do this anymore, you can focus on [better things](https://www.google.com/search?q=how+to+contribute+to+open+source).

----

# CODE!

This heavily depends on the tooling available.

(But you can also introduce new tools!)

----

# CRUD

Almost all "jobs" should have:

1. Create
2. Read
3. Update
4. Delete

----

# Ansible

----

# Reuse code

[https://galaxy.ansible.com/](https://galaxy.ansible.com/search?keywords=update%20&order_by=-relevance&page=1&deprecated=false&type=role)

----

# Make a playbook

```yaml
- name: Prepare
  hosts: all
  become: yes
  gather_facts: no

  roles:
    - role: robertdebock.bootstrap
    - role: robertdebock.update
```

----

# Try it

```shell
ansible-playbook update.yml \
  --inventory my_test_host, \
  --check
```

```shell
ansible-playbook update.yml \
   --inventory my_test_host,
```

----

# Run it

```shell
ansible-playbook update.yml
```

---
# Almost there

Automation has saved you time, cool!

----

### How can you do even less?

----

## Scheduling automation

Sure, `cron` or [awx](https://github.com/ansible/awx/)

- Limitations?

----

## Let others do it. (&trade;)

Much better, but what if she/he is on a holiday?

----

## Let the owner do it.

---

# How to organize

----

# By product and service

For example:

- Operating system team
- Backup & Restore team
- Monitoring team
- Compliance team
- Orchestration

---

# How to develop

- Choose a language
- Train people
- Organize learning sessions
- Invite people from another team

----

# Mindset

All teams must offer an API to allow self-service capabilities for their product or service.

---

# Conclusion

1. Automation allows scaling
2. Automation brings predictability
3. May require re-organizing teams
