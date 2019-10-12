# Part 2: ⚒️ Netlify Build

- Netlify ❤️ Build Tools and SSGs
  - [StaticGen.com](https://url.netlify.com/ryQFMscwr)
  - [Modern-Static-Website-Generators-Next-Big-Thing](https://www.smashingmagazine.com/2015/11/modern-static-website-generators-next-big-thing/)
- Understand The Build Process
  - You can always local build!!! You May Not Need CD™ but it's better to have if the project is open source or if you are working in a team.
  - Build Settings and where to set them.
    - [Build Settings Docs](https://url.netlify.com/Syr5ficPH)
    - In app
    - netlify.toml (overrides the build command given in deploy settings of Netlify)
  - the Build Bot
    - [How Netlify Works and role of build bots.](https://url.netlify.com/BJMifs9wS)
    - [https://github.com/netlify/build-image/blob/master/run-build.sh](https://github.com/netlify/build-image/blob/master/run-build.sh)
  - Build stages and Reading Logs
    - [Netlify App Logs](https://url.netlify.com/SJEpGi9wH)
    - [Netlify Site Logs](https://url.netlify.com/BykRMi9Pr)
    - Fetch from cache
      - NETLIFY_CACHE_DIR = "/opt/build/cache"
      - [Cool Side Project by David Wells cache-me-outside how bout dat :p](https://github.com/DavidWells/cache-me-outside)
    - Install
    - Build
    - Package & optimize
    - Save cache
    - (post processing)
    - Deploy
    - Output manifest
  - Concurrent Builds and Canceling Builds
  - Gotchas
    - [Common Build Gotchas](https://url.netlify.com/H1hAMocDH)
    - 15 min rule (Need to inform Netlify if the build isn't successful in 15 minutes, or upgrade from free tier.)
    - Permissions and API Secrets
    - Think about what folder you are deploying
    - Community Build tips [https://url.netlify.com/BJjJ7jqDH](https://url.netlify.com/BJjJ7jqDH)
  - Troubleshooting
    - Read your build logs
    - Make sure you can build locally
    - Hidden Dependencies
      - Environment version
      - Yarn vs npm
      - Preinstalled Grunt/Hugo/Bower etc
    - Netlify Community [https://url.netlify.com/BysgQs5wS](https://url.netlify.com/BysgQs5wS)
- Environment Variables
  - Where to set them
  - [https://gist.github.com/sw-yx/c53634e7e63f0015e43c16bc26832283](https://gist.github.com/sw-yx/c53634e7e63f0015e43c16bc26832283)
  - [https://scotch.io/@sw-yx/netlify-environment-variables-the-cheat-codes-of-the-internet](https://scotch.io/@sw-yx/netlify-environment-variables-the-cheat-codes-of-the-internet)