# Ansible Role: Jenkins

Install jenkins & jenkins modules on Ubuntu.


## Role Variables

See defaults/main.yml


## Example Playbook

    - hosts: vagrant
      remote_user: vagrant
      sudo: yes

      vars:
        jenkins_plugins:
          - build-pipeline-plugin
          - git
          - git-parameter
          - groovy-postbuild
          - jobConfigHistory
          - slack
          - timestamper

      roles:
        - { role: jenkins }


## Example Output

    PLAY [all] ********************************************************************

    GATHERING FACTS ***************************************************************
    ok: [default]

    TASK: [jenkins | Add Jenkins apt key] *****************************************
    ok: [default]

    TASK: [jenkins | Add Jenkins repository to sources] ***************************
    ok: [default]

    TASK: [jenkins | Update APT package cache] ************************************
    ok: [default]

    TASK: [jenkins | Install Jenkins] *********************************************
    ok: [default]

    TASK: [jenkins | Ensure Jenkins is started and runs on startup] ***************
    ok: [default]

    TASK: [jenkins | Wait for Jenkins to start up before proceeding next step] ****
    ok: [default]

    TASK: [jenkins | Get the jenkins-cli jarfile from the Jenkins server] *********
    ok: [default]

    TASK: [jenkins | Create Jenkins updates folder] *******************************
    ok: [default]

    TASK: [jenkins | Update Jenkins plugin data] **********************************
    ok: [default]

    TASK: [jenkins | Permissions for default.json updates info] *******************
    ok: [default]

    TASK: [jenkins | Install Jenkins plugins] *************************************
    ok: [default] => (item=build-pipeline-plugin)
    ok: [default] => (item=git)
    ok: [default] => (item=git-parameter)
    ok: [default] => (item=groovy-postbuild)
    ok: [default] => (item=jobConfigHistory)
    ok: [default] => (item=slack)
    ok: [default] => (item=timestamper)

    TASK: [jenkins | List plugins to be updated] **********************************
    ok: [default]

    TASK: [jenkins | Update plugins] **********************************************
    skipping: [default]

    PLAY RECAP ********************************************************************
    jenkins | Update APT package cache ------------------------------------- 28.14s
    jenkins | List plugins to be updated ------------------------------------ 2.15s
    jenkins | Add Jenkins apt key ------------------------------------------- 1.32s
    jenkins | Install Jenkins plugins --------------------------------------- 0.97s
    jenkins | Install Jenkins ----------------------------------------------- 0.70s
    jenkins | Add Jenkins repository to sources ----------------------------- 0.23s
    jenkins | Wait for Jenkins to start up before proceeding next step ------ 0.20s
    jenkins | Ensure Jenkins is started and runs on startup ----------------- 0.19s
    jenkins | Permissions for default.json updates info --------------------- 0.16s
    jenkins | Get the jenkins-cli jarfile from the Jenkins server ----------- 0.16s

    Playbook finished: Sat Jan  9 18:19:43 2016, 13 total tasks.  0:00:34 elapsed.

    default                    : ok=13   changed=0    unreachable=0    failed=0


## License

MIT / BSD
