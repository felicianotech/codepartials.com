---
title: "Deploy a Project Using RSYNC"
tags:
  - deployment
  - rsync
  - ssh
---

```
      - deploy:
          command: |
            if [ "${CIRCLE_BRANCH}" == "master" ]; then
              echo 'web01.revidian.net ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBJiGRY6N9WYQ0vy6cTiwAgNbc6ueJmVo/EafBtmT7bcD6cQMbipYM/KfYQ2lCn2TxqWepZKYoyoVQXgArycCOns=' >> ~/.ssh/known_hosts
              rsync -va --delete src/public/ staticweb@web01.revidian.net:www/codepartials.com/public_html
            fi
```
