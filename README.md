# Concourse pipeline for https://github.com/FINkit/buildstack-boshrelease
fly -t concourse auth

fly -t concourse set-pipeline -c pipeline.yml -p concourse-buildstack-boshrelease --load-vars-from credentials.yml

fly -t concourse trigger-job -j concourse-buildstack-boshrelease/task -w --verbose

