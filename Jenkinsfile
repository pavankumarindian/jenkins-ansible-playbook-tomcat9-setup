---
- name: install and configure tomcat9
  hosts: 10.0.0.58
  become: yes
  tasks:
    - name: install tomcat9
      ansible.builtin.apt:
        name: tomcat9
        state: present
        update_cache: yes
    - name: change port of tomcat9 from 8080 to 9000
      replace:
        regexp: 8080
        replace: 9000
        path: /etc/tomcat9/server.xml
    - name: restart tomcat9
      service:
        name: tomcat9
        state: restarted
