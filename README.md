# helm-charts

Helm Charts for tKeel

## Quick Start

This guide will walk you through a series of steps to package, upload and deploy helm charts. 

The following steps in this guide are:

 - Clone the repository
 - Create robots.txt
Use the Dapr API
Configure a component
Explore Dapr quickstarts


### Step 1. Fork

1. Visit https://github.com/tkeel-io/helm-charts
2. Click `Fork` button to create a fork of the project to your GitHub account.

## Step 2. Clone the repository
```
$ git clone https://github.com/tkeel-io/helm-charts.git && cd helm-chart/
Cloning into ‘helm-chart’…
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.
```

## Step 3. Lint the chart

As a good habit, helm lint runs a series of tests to verify that
the chart is well-formed:

```bash
$ helm lint ../you-project/charts/*
```

## Step 4. Create the Helm chart package

```bash
$ helm package ../you-project/charts/*
Successfully packaged chart and saved it to: /Users/iot/git/helm-chart/helm-chart-test-0.1.0.tgz
```

### Step 5. Create the Helm chart repository index

```
According to Helm:
A repository is characterized primarily by the presence of a special file called index.yaml that has a list of all of the packages supplied by the repository, together with metadata that allows retrieving and verifying those packages.
So, everything we need to create is the index.yaml file and the command to do that is:
$ helm repo index --url https://mattiaperi.github.io/helm-chart/ .
$ cat index.yaml
apiVersion: v1
entries:
helm-chart-test:
- apiVersion: v1
  appVersion: "1.0"
  created: 2019-04-16T11:10:08.729944+02:00
  description: A Helm chart for Kubernetes
  digest: 35a4e31bfacc496f1b1bce664652916bb8701cc9df77f1b90534f5234ff297a6
  name: helm-chart-test
  urls:
    - https://mattiaperi.github.io/helm-chart/helm-chart-test-0.1.0.tgz
      version: 0.1.0
      generated: 2019-04-16T11:10:08.729368+02:00
```

### Step 6. Commit local changes

```
git add <file>
git commit -s -m "add your description"
```

### Step 7. Push to your fork

When ready to review (or just to establish an offsite backup of your work), push your branch to your fork on GitHub:

### Step 8. Create a PR

Visit your fork at https://github.com/$user/helm-charts
Click the Compare & Pull Request button next to your branch.
Check out the pull request process for more details and advice.

