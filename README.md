# GoLang IAST Sample App

This application is based on the Frontend component of the GCP Micrservices-Demo project [found here](https://github.com/GoogleCloudPlatform/microservices-demo).  It's intended to show a simple example of a Golang app with New Relic's IAST capability installed and enabled.  You can then follow the same coding pattern to enable IAST in your Golang app.

Please note that this application contains no IAST findings. No IAST vulnerablities will be shown in the New Relic UI.

To see how this app enables APM and IAST, review the code in `main.go`.  The `import()` stanza includes the required `newrelic` and `nrsecurityagent` modules.  Starting at line 150, the `main()` function instantiates the New Relic APM agent and the IAST capability.

If you want to run this app to see it report to your New Relic account, do the following:

1. Replace the placeholder in the included `setup.sh` file with a valid New Relic license key.
1. Source `setup.sh` to properly configure the environment so the app will run:
    `. ./setup.sh`
1. Build the application with:
    `go build
1. When the build is complete, a binary called `frontend` should have been created.  Run it as follows:
    `./frontend`

You should then be able to go into the New Relic UI and see an application called `Test-GoApp` and see it appear in the IAST portion of the UI.  You can verify proper operation by looking at the log files in the `nr-security-home` directory which will be created when you run the app for the first time.  You can also look at the app's console output to see diagnostic information if APM or IAST is not successfully loaded.

This application was successfully built and tested under Go 1.21.0.
