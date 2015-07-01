# Bigtop deployment on already existing cluster

This ansible playbook deploys upcoming 1.0.0 release (current master) of Apache
Bigtop Hadoop distribution on already existing cluster (so both virtual and
real machines are ok). Basically the playbook automates most of the steps
described in this quick howto from Apache Bigtop cwiki:
[How to install Bigtop 0.8.0 Hadoop on CentOS 6 with Puppet](https://cwiki.apache.org/confluence/display/BIGTOP/How+to+install+Bigtop+0.8.0+Hadoop+on+CentOS+6+with+Puppet)
(note that this playbook was designed for 1.0.0 release and not 0.8.0).

Don't be deceived by the fact that this is an ansible playbook! Bigtop puppet
recipes uses master-less mode and so ansible has just two main goals here:
install all requirements and then run `puppet apply`, both on all machines of
the cluster. Puppet recipes does all the hard work of setting up Bigtop Hadoop
components.
