# this is used for comment (single hashtag) | git bash always stars with dollar sign so no dollar sign is presented before commands
# most often used symbols: ~ | $ | <#>

# First step is we need to get in touch with github
# For now I have already created a repo (repository) called new_repo on Github.
# The command below show on how to connect to new_repo using this command:
# git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
$ git clone https://github.com/reposit96/new_repo.git # everything is fine.

# Second step is to initialize .git files to your local repository by using this command shown below:
git init # unless it's already was initiliazed we will get a message for reinitialization being made upon. It's okay no worries!

# Third step is git bash straight away from local repository or follow command below:
cd ~/My-Github-Project/new_repo # ~ might need be changed to full path such as mine /c/Users/Lukas_G/My-Github-Project/new_repo
# In order to show files files and (or) folders (to get know better what files are you working with), follow command below:
git ls-files # if no files is shown it might be due to files not been added (added, tracked, staged – all're synonyms) yet.
# We allways have to track first using < $ git add > command, then by tracking we prepare file or (and) folders for staging (stage)
# https://stackoverflow.com/questions/572549/difference-between-git-add-a-and-git-add | First TRACK then STAGE

