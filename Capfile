#################### UNCOMMENT FOR MULTISTAGE DEPLOYS ####################
#require 'capistrano/ext/multistage'
#
#set :stages, %w(stage1 stage2)
#set :default_stage, "stage1"
#
## You'll also need to modify the following files:
## config/deploy/stage1
## config/deploy/stage2
##########################################################################

## Here's a link to the capistrano Getting Starting Page
# https://github.com/capistrano/capistrano/wiki/2.x-Getting-Started

## Here's a link to the capistrano handbook
# https://github.com/leehambley/capistrano-handbook/blob/master/index.markdown

############################## INSTRUCTIONS ##############################
### Replace REPOSITORY with your Repository's name (from github)       ###
### Replace PROJECT with your Organization's name (from github)        ###
### Replace description and provide executable information             ###
### Uncomment description and executable lines                         ###
### Add ADDITIONAL_EMAIL_RECIPIENTS if desired                         ###
##########################################################################
set :application, "tup"
set :repository,  "git://github.com/dunedain289/tup.git"
set :deploy_to, "/n/dv/release/tup"
#set :description, "DESCRIPTION OF THE PROJECT"
#set :executables, [{name: "SCRIPT_NAME", summary: "SCRIPT_SUMMARY", details: "SCRIPT_DETAILS"},{...},...]

## By default, the last 20 releases are kept, but that can be modified:
#set keep_releases, 20

### Email Instructions ###
## By Default, anyone who has ever touched the repository will get an email
## on a deploy. To disable this functionality, uncomment the following line:
set :email_contributors, false

## You can add additional email recipients:
#set :deploy_recipients, %w(someone@centtech.com someone_else@centtech.com)

## You can remove remove individuals who no longer want email:
#set :recipients_blacklist, %w(thuang@centtech.com)

## You can change the host on which the deploy is run
#set :deploy_host, "hostname"

## You can add hosts that will only run certain tasks:
#role :build, "hostname", :no_release => true

require 'centaur_deploy'

## You can disable the remote vs local repo check:
#set :check_local_synced_to_remote, false

namespace :deploy do

  ## You can add custom tasks for whatever you might need
  # desc "Do some custom steps needed for a deploy"
  # task :custom_task do
  #   run "cd #{release_path} && make check"
  # end
  ##
  # desc "Build the code"
  # task :build_task, :roles => :build do
  #   run "cd #{release_path} && make all"
  # end

  desc <<-DESC
      You can override this task to do any additional steps you \
      might need in your deploy process.  (i.e. builds, checks, \
      server restarts)
  DESC
  task :additional_tasks do
    run "cd #{release_path} && ./build.sh"
  end

end

