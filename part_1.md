# Part 1: 🗺️ Netlify Edge

- 4 methods

- Netlify Drop : Originated from BitBalloon where you could drag and drop a folder and have it deployed immediately on a CDN.

- Select the folder and drop it again under the deploy section area to update the changes you made.

- We can

- Netlify CLI: **Deserves Separate Set of Notes** but here we cover just the basics.
- Type in npm install -g npm to install netlify.
- netlify login to log in and netlify status to verify if login was successful.
- netlify help for other commands.

- ntl deploy or netlify deploy for deploying the site. Select current directory by typing "." as address. Then check on test url if preview is fine. Then deploy to production using netlify deploy --prod.
- .netlify folder has a json file which stores the site ID i.e. to which site you have linked this code to.
- ntl status inside a linked folder tells us to which site and via which user this code is linked to and location where it is deployed, along with admin url and site ID.
- git init
- git add . >> git commit -m "First commit" >> Go to GitHub make a new repo >> Go folder in your terminal and type git remote add origin git@github.com:UserName/repo_name.git
- Do a git pull origin master --allow-unrelated-histories (Just in case to solve README.md conflict and similar issues."
- Do a git add . >> git commit -m "Fix merge issues." >> git push -u origin master.
- You can see your changes on the website now and with this we are well on our way to set up Continuous Deploy to Netlify.
- Setting up Build Hooks can be done by going to Deploy >> Deploy Settings >> Build Hooks >> Add Build Hooks.
- Give the hook a name and give it a branch to build and then copy the curl command generated.
- Paste the curl command in master of your repo and run. Build hooks can be used for triggering events periodically or based upon if/then conditions.

- **Continuous Deploy to Netlify**
- Go to Netlify Homepage
- Select New site from Git >> Choose Provider >> Select repo >> If netlify.toml exists then directory to publish gets detected automatically.
- Once you deploy from git then Continuous Deployment (CD) and build happens automatically.
- To stop CD for git connected website click Stop Auto Publishing in the deploys section.
- After stopping the auto publish we see that in deploys section after push to github we may see

- Deploy Hooks

- Private repos https://url.netlify.com/rJ-WZsqwS

- **Deploy to Netlify Button** - Useful for OpenSource Projects
- To set this up you need to have netlify.toml set up properly.
- Go to this [link](https://www.netlify.com/docs/deploy-button/) and neter your repo address and copy MD snippet shown, you will get a button like this:
  [![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/AnmolTomer/vitcmun-20_test)

- [Check this out for private repos](https://url.netlify.com/SkmMWo5wH)
- Having a Deploy button allows users who are not the creator to have a deployed independent version with which they can experiment and see features they want to implement being deployed in real time and allows the person who used the button to have latest updates that creator makes to their deployment along with a fork on which they can work.
- more ways (Siri, Wand, Watch, CodeSandbox) https://url.netlify.com/rkRMZjcPB
- Netlify also gives deploy previews as well. Say you make a new branch as following:
- git checkout -b newFeature >> git add . >>git commit -m "TEST">>git push origin newFeature then create a new PR on GitHub. We write the info of PR and click Create PR. Upon clicking Create PR and on doing this some checks occur which do not occur on normal sites. This is a deploy preview along with some tests which occur.
- On doing merge of PR, new build kicks off in Master branch.
- All of the deploys are distributed to nearest point of presence resulting in faster load time.
- Deploys are atomic i.e. Netlify waits until all the files are uploaded before pushing everything to the production, so that customers never see a kind of a half updated site.
- Instant rollback also exists.If you need to go back.
- Asset Optimization: Deploy Settings->Post Processing->Asset Optimization->Deploys->Re-trigger Deploy
- Customising the URLs that customers see - Go to deploy settings and change site name and not use the random ones.
- Say we have an about.html page and on going to netlify.com/about we can see this but sometimes we want redirection from netlify.com/aboutus to netlify.com/about on its won then what we do is create a \_redirect file and write it in format from to F.e. /aboutus /about and for 404 we do catch all using /_ /404 to send every request to 404.html page and /_ /index.html to send everytime to index page.
- If we use JS to request JSON files then sometimes it gets redirected and we get back html instead of JSON.

# Custom Domain

- Go to settings Domain Management, netlify offers free custom domains i.e. if you have a domain already purchased then you can verify and add it or you can buy a domain through Netlify too.
- There's Netlify DNS service which is used to provide additional features, user can also enable IPv6.
-
- Functions
- add a sample JS and Go function

- setting Functions folder in app

- setting Functions folder in netlify.toml

- Event Triggered Functions

- `deploy-building`, `deploy-succeeded`, `deploy-failed`, `deploy-locked`, `deploy-unlocked`

- Env variables

- INCOMING_HOOK_TITLE, INCOMING_HOOK_URL, INCOMING_HOOK_BODY https://url.netlify.com/ryqXbo5Pr

- AWS Lambda versions: AWS_LAMBDA_JS_RUNTIME nodejs10.x

- Defaults

- [HTTPS](https://url.netlify.com/S1LVbsqDH)

- [Deploy Previews](https://url.netlify.com/By4cWi5Pr)

- [Branch deploys](https://url.netlify.com/HyBHboqvB)

- Split testing

- `split-test-activated`, `split-test-deactivated`, `split-test-modified`

- Distributed Deploys, Atomic Deploys, Instant Rollbacks

- Post Processing

- Forms **separate video**

- Mixed Content

- Prerendering https://url.netlify.com/S1Hj-i9wr

- [Asset Optimization](https://url.netlify.com/r1fnZjqvS)

- Netlify Large Media

- https://url.netlify.com/HyRnZsqDH

- Snippet Injection

- for GA, eg its more involved if you do it in Nuxt

- Netlify and Custom Domains

- Custom Netlify Domain

- Redirects

- `_redirects` file

- netlify.toml version

- Redirects Playground https://url.netlify.com/Syk0-s5wB

- Headers

- `_headers` file

- netlify.toml version

- Headers Playground https://url.netlify.com/SJlkMiqDr

- Cache control https://url.netlify.com/By2kfoqwr

- Auth headers https://url.netlify.com/HkLlfjcwr

- [Custom Domains](https://url.netlify.com/B16efs9vr)

- Netlify DNS

- DNS Docs https://url.netlify.com/Bk5-GsqwB

- Community Common Issue: Should you use Netlify DNS? https://url.netlify.com/Sy_MficDr

- Migrating to Netlify DNS with minimal downtime https://url.netlify.com/HykBGocvB

- Emails https://url.netlify.com/SkWIMi5PH

- CDN Tips

- Faster deploys https://url.netlify.com/BJiLMscDB

- Enterprise https://url.netlify.com/B1zvGsqDS
