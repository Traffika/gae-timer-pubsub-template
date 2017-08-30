# GAE Timer Pub/Sub Template
This is the GAE project template to setup timer based pub-sub in GCP

### To use:
- Clone this repository
- Modify the `cron.yml` file to update the pubsub topics


## cron.yaml

The cron.yaml file is a descriptor for the App Engine Cron Service that is the service timer for the cloud functions.
This file contains all the cron jobs for all the checklist apps.


#### How to

- Create a service account with Project Owner capabilities
- Furnish a new JSON key - download and save key (called 'credentials.json' from here, onwards)
- Run `gcloud auth activate-service-account --key-file credentials.json`
- Can now deploy using: `gcloud app deploy cron.yaml --project={ PROJECT NAME GOES HERE }`



#### Notes

**Example times:**

```
every 12 hours
every 5 minutes from 10:00 to 14:00
every day 00:00
every monday 09:00
2nd,third mon,wed,thu of march 17:00
1st monday of sep,oct,nov 17:00
1 of jan,april,july,oct 00:00
```



**To authorize:**

`gcloud auth activate-service-account --key-file credentials.json`



**To deploy:**

Set the project:

```shell
gcloud config set project { PROJECT NAME GOES HERE }
```


```shell
gcloud app deploy cron.yaml --project={ PROJECT NAME GOES HERE }
```


**To delete:**

The `cron-delete.yaml` file must be empty to delete all the cron jobs - you will want to re-add the existing ones.

```shell
gcloud app deploy cron-delete.yaml --project={ PROJECT NAME GOES HERE }
```


For more info see [https://cloud.google.com/appengine/docs/flexible/nodejs/scheduling-jobs-with-cron-yaml](https://cloud.google.com/appengine/docs/flexible/nodejs/scheduling-jobs-with-cron-yaml)
