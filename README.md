# Build Vue and deploy it to Github Pages 🚀

This Action will Build your Vue Project and deploy it to Github Pages

## Getting Started 🎉

1. Create the `vue.config.js` file
2. Add this to your `vue.config.js` (and rename "YourRepoName" to your repo name)

```javascript
module.exports = {
    publicPath: '/YourRepoName/'
}
```

3. Create a Github Actions Workflow file and add this to it (and replace "YourGithubName" and "YourRepoName" with the names)

```yml
name: Build Vue
on: [push]
jobs:
  build_vue:
    runs-on: ubuntu-latest
    name: Build Vue
    steps:
    - uses: actions/checkout@v2
    - id: Build-Vue
      uses: alexvoedi/VuePagesAction@1.0.0
      with:
        username: 'YourGithubName'
        reponame: 'YourRepoName'
        token: ${{ secrets.GITHUB_TOKEN }} # Leave this line unchanged
```

4. Go to Settings -> Scroll down to GitHub Pages -> Select `gh-pages` as branch and `/` as directory

## Options 🔧

|      Name      |            Description           |     Default    | Required |
| :------------: | :------------------------------: | :------------: | :------: |
|    username    |           Your username          |        -       |    yes   |
|    reponame    |       Your repository name       |        -       |    yes   |
|      token     | Please leave this line unchanged |        -       |    yes   |
|    gitbranch   |          Git branch name         |      main      |     -    |
|    gitemail    |         Git commit email         | CI@example.com |     -    |
|     gitname    |          Git commit name         |       CI       |     -    |
|     gitmsg     |        Git commit message        |     deploy     |     -    |
|      cname     |           Custom domain          |        -       |     -    |
| packagemanager |     The used packgage manager    |       npm      |     -    |
