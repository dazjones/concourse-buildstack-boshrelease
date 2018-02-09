# Concourse pipeline for https://github.com/FINkit/buildstack-boshrelease
fly -t concourse auth

fly -t concourse set-pipeline -c pipeline.yml -p <name> --load-vars-from credentials.yml

fly -t concourse trigger-job -j <name>/<task> -w --verbose

