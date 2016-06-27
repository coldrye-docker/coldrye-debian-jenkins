# vim: noexpandtab:ts=4:sw=4

provider = coldrye
os = debian
release = jessie
feature = jenkins
feature_version = 2.10
tag := $(shell date +"%Y%m%d%H%M%S")
image = $(os)-$(feature)
deploy_dir=/var/lib/jetty
storage_dir=/var/storages/jenkins

include ../../Makefile.war.in

