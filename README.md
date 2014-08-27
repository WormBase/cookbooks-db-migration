ABOUT
================

This repository contains Chef recipes for building and 
configuring instances related to the database migration project
at WormBase:

   http://www.wormbase.org/
  
Todd Harris


ACKNOWLEDGEMENTS
==================

chef-aws-tag:
Because I couldn't see how to use more than a single custom chef recipe 
repository in AWS OpsWorks, "chef-aws-tag" was lifted unmodified
from Stuart Warren and placed alongside our other recipes.

   https://github.com/stuart-warren/chef-aws-tag

Thanks, Stuart!



RECIPES
========


chef-aws-tag
============

Set tags on your ec2 instances using Opsworks

How?
====

Add ``aws-tag::ec2`` recipe to your layers runlist

Add a section to your custom json and set your own list of tags, eg:

```
{
    "aws-tag": {
        "tags": {
            "ouid": "917736014",
            "team": "webdev",
            "email": "email@company.com",
            "app": "Awesome App",
            "environment": "dev",
            "availability": "on"
        }
    }
}
```

Ensure that the opsworks role has the ability to CreateTags and DeleteTags.
