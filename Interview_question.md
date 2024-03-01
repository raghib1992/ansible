################################
# Based on both the supplied example payload and variable file
# please confirm what each of the 3 DEBUG statements evaluates as
#
# Assume all conditional statements evaluate to TRUE
#
www_artifacts_list = g4www, g4www_config, g4www_schema
################################

- name: Set WWW variables
  set_fact:
    www_artifacts_list: "{{ www_deployment_limit|replace('-','_') }}"
  when:
    - app_name == "www"
    - deployment_designation is not defined
  tags: interview

- debug: var=www_artifacts_list
  when:
    - app_name == "www"
    - deployment_designation is not defined
  tags: interview

- name: Set WWW tags
  set_fact:
    www_tags: "{{ www_tags }} + ['{{ www_app_tags[www_artifact] }}']"
  with_items:
    - "{{ www_artifacts_list.split(',') }}"
  loop_control:
    loop_var: www_artifact
  when:
    - app_name == "www"
    - deployment_designation is not defined
  tags: interview

- name: Set WWW deployment tags
  set_fact:
    www_deployment_tags: "{{ www_tags | unique | join(',') }}"
  when:
    - app_name == "www"
    - deployment_designation is not defined
  tags: interview

- debug: var=www_deployment_tags
  when:
    - app_name == "www"
    - deployment_designation is not defined
  tags: interview
  
 - name: Set WWW host limits
  set_fact:
    www_limit_hosts: "{{ www_limit_hosts + www_tag_limits[www_limits] }}"
  with_items:
    - "{{ www_deployment_tags.split(',') }}"
  loop_control:
    loop_var: www_limits
  when:
    - app_name == "www"
    - deployment_designation is not defined
    - silo_deployment is not defined
  tags: interview

- name: Set WWW deployment host limits
  set_fact:
    www_host_deployment_limit: "{{ www_limit_hosts | unique | join(',') | default('') }}"
  when:
    - app_name == "www"
    - deployment_designation is not defined
  tags: interview

- debug: var=www_host_deployment_limit
  when:
    - app_name == "www"
    - deployment_designation is not defined
  tags: interview
  
  
  ##################################
  
  Answers:
  
  Debug statement 1: g4www,g4www_config,g4www_schema
  Debug statement 2: g4www,g4wwwg4www,g4wwwg4wwwg4www
  Debug statement 3: drupali,g4mau,varnishali