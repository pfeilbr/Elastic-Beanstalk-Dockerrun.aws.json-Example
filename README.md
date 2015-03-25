# Elastic Beanstalk Dockerrun.aws.json Example

This example uses the [elasticsearch docker image](https://registry.hub.docker.com/_/elasticsearch/) as an example.  Once running you can visit `http://<beanstalk doamin>/?pretty` an you should see the elastic search JSON.

## Initial Deployment

1. Modify `Dockerrun.aws.json` for your needs.

2. Commit changes to repo

	```bash
	$ git commit -a -m "changes"
	```

	> assumes `Dockerrun.aws.json` has already been added to repo.  if not, `git add .`

3. Create eb app

	```bash
	$ eb init # populate details
	```

	> NOTE: select Docker.  Populate all details

4. Create environment for app

	```bash
	$ eb create dev-env
	```

	> **IMPORTANT** Must immediately update the ec2 instance with tags so it doesn't get terminated.  Enable termination protection on the ec2 instance.

## Deploying Updates

1. Modify `Dockerrun.aws.json` for your needs.
2. Commit changes

	```bash
	$ git commit -a -m "my updates"
	```

3. Deploy to eb

	```bash
	$ eb deploy
	```

> NOTE: Takes between 3-5 min to deploy changes

## Notes

Port mapping details specific to aws beanstalk

![](http://note.io/1xzEypO)
