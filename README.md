# Project: Search UI

Purpose of this repository is to provide MWS pages with the proper JS and CSS assets to achieve a working search page with the vendor's (Coveo) technology called Headless.

## References

- Coveo Headless: https://docs.coveo.com/en/headless/latest/

## Key details

### Sponsor / Contact

This project is led by Principal Publisher at ESDC. The key contact in case of questions related to the project is Francis Gorman, who can be reached at francis.gorman@hrsdc-rhdcc.gc.ca. If no reply is received from this person, fallback contact is ESDC.SD.DEV-DEV.DS.EDSC@servicecanada.gc.ca.

### Timeline and frequency

The goal is to continue to refine and improve this code base on a regular basis. Every 6 months, if no activity is recorded on this repository, the key contact shall be reached out to in order to ensure it isn't stale.

**Removal date** will coincide with end of contract with vendor.

### Improvement plan

To manage development activities related to this project, a standard internal issue tracking system used at Principal Publisher will be used. Also, regular touchpoints with the search vendor, as well as formal service requests entered through their portal, could also spark some development activities from a vendor perspective.

In the medium to long term, some activities may take place related to:
- stabilization of the query suggestion combobox;
- porting of some parts of the codebase to GCWeb;
- addition of machine learning features.

## Releases and API

All changes contributed through Pull requests will be packaged as releases. Releases are completed through the "Releases" tab in this GitHub repository; then, deployment to MWS follows the reguar release management cycle accordingly.

Each new verion of this project is defined based on an evaluaton of the impacts of changes against any formerly up-to-date Search UI implementation. The scope constitutes of all files within the "dist" folder (distribution files), which are JavaScript scripts and CSS styles.

Search UI follows [Semantic Versioning 2.0.0](https://semver.org/)

---

## To do

[Consult full checklist of to do items](todo.md)

---

## Getting started

This rubric is for developers

### Build files

1. run: npm install -g grunt-cli
2. run: npm install
3. run: grunt (build script; tasks to lint, test & minify content in "dist")

### Test as end-user

1. Push to a branch in your origin remote, in a branch of your choice. It is recommended that you use a dedicated branch for testing, which is different from one where you would be opening a Pull request from.
2. Make sure your repository has GitHub Pages enabled, on that specific above-mentioned branch.
3. Since you need a token to communicate with the Coveo API, you can do the following to go to get a token valid for 24 hrs:
    1. Go to a search page on the Canada.ca preview such as: **/en/sr/srb.html**.
    2. Open the inspector (developer tool) and look for the `div` tag that has the attribute called `data-gc-search`.
    3. Inside this attribute, you'll find a Javascript object that has a field called `accessToken`. Grab the value of that token.
    4. Replace `XYZ` with the token on any page within the /test/ folder of this project, such as **srb-en.html**.
    5. If you are planning on opening a pull request with your changes, do not forget to put `XYZ` back into the files.
    6. If the token doesn't seem valid, take another one from the Canada.ca Preview server or you may have passed the 24 hours TTL of the token; get another one.

### Deployment

1. Take the content of the "dist" folder and put it on a server. Make sure you have a mechanism in place to handle a key/token
