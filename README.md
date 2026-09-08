Deploy a todo application using the docker compose file into render, Atually this repo contains the both frontend,backend with different folders.
steps from scratch how the workflow will works, if any developer commits any code and create a PR it will first run the test.yaml actions.
.github/workflows contains the test.yml-- it contains jobs to check the lint
    lint - pnpm lint
    test - pnpm test
the above two commands will checks the lint and tests of the code if any issues it found it will fails the PR, Adtionally we added a build steps in PR yaml and also added a trivy scan for it, if the trivy will found any vulenrabilities or any severity issues it found PR will failed. we have checked this by c reating a PR this code contains some vulenrabilities PR got failed - https://github.com/Maddalarajesh/G3-Assigment/pull/1
Docker-compose files contains a services and volumes and api and frontend we have it will create multi containers at a time when we run the command docker compose up -d .
The dockerfiles we have added in related folders means frontend dockerfile is in frontend folder and backend is in folder. we added a multi stage because the docker image will have a leightweight images and it will installs and have the necessary application dependencies only.
Once everything looking good in the PR if they push the changes to main branch build.yaml will start executing it will build, tag and push those images into dockerhub.
