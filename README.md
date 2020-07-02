# GoMEco
A Integrated Systems Ecology Lab project looking into changes in the structure and function of the Gulf of Maine ecosystem, with particular focus on apex predators and key forage species.

# Project structure
This collaborative lab project uses both GitHub and Box to facilitate sharing data and code. First, to get set up:

## GitHub bits
1. Go to https://github.com/GMRI-SEL/GoMEco and fork the repository to your account.
2. When the fork is complete, you should be looking at your online copy of the GoMEco repo. From there, to be able to communicate easily between your local machine and GitHub online, you will want to clone your forked copy of the repo to your machine. There are a variety of different ways to do this, but one easy way is to just start a new version controlled RStudio project. After you select "Git" as the version control option, you will be asked for the repository url. Get this by copying the path on GitHub online to your forked copy of the repo. It should be something like: https://github.com/aallyn/GoMEco.git, except instead of "aallyn" it will have your user name.
3. Now you have a forked copy of the lab project repo on Github online and on your local machine. But, you still won't be able to easily communicate with the lab project repo. To do this, you will need to establish an upstream connection with the original lab project repo. You can establish this connection by opening up a new terminal window and then:
    - cd "pathtorepo" where the "pathtorepo" is just the local path to where you have your cloned copy of the lab project. For example for me I would do:
        + cd ~/GitHub/GoMEco 
    - git remote add upstream https://github.com/GMRI-SEL/GoMEco.git
    - git pull upstream master --ff-only
4. Alright, I think you now should be good to go. You can work locally, push to your forked copy of the lab project repo and then submit a pull request so that your changes can be incorporated into the original lab project repo. Similarly, you can pull from upstream to make sure that you have any changes made on the original lab project repo.

## Box and code structure bits
Now that you've got everything set up, I would suggest that at the beginning of everyone's code they source the lab function that loads paths to GMRI folders:

`source("https://raw.githubusercontent.com/GMRI-SEL/LabFunctionsandCode/master/GenerateSharedPathsScript.R")`

In particular, this should make it really easy to access data for this project, which will be kept on Box at `Box/Mills Lab/Projects/GoMEco/Data/`. For example, to load in the population estimates, you would do something like:

`pop.dat <- read.csv(paste(proj.path, "Data/GoMSeabirdData - GoMSeabirdPopEstimates.csv"), sep = "")`

Still working on the best way to do this, but for now, I think this will work. When you source the function, it will load: res.data.path, res.func.path, lab.data.path, lab.func.path and proj.path.
