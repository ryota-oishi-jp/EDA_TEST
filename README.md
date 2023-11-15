# EDA_TEST
---
- name: Hello Events
  hosts: all

  sources:
    - ansible.eda.webhook:
        host: 0.0.0.0
        port: 5000

  rules:
    - name: Say Hello
      condition: event.payload.message == "sakana"
      action:
        run_job_template:
          name: Demo Job Template    # 実行したいジョブテンプレート名
          organization: Default
