## Lab 2
## Create Chef Cookbook using chef generate
Allotted Time: 20 minutes

In this activity, you will generate a sample cookbook using the chef generate command. This will be a quick review for many, the essentials to generate the cookbook, create a kitchen.docker.yml file and converge the node. This will verify that you know the essentials for creating and converging on your system and that everything is working correctly. 

Create cookbook and an install_apache recipe.

```
 $ cd ~/wd
 $ chef generate cookbook -I apachev2 apache
 $ cd apache
 $ chef generate recipe . install_apache -I apachev2
 $ vi recipes/install_apache.rb

```

Add the follow `resources` to the `install_apache` recipe.

```
package 'apache2'

service 'apache2' do
  action [ :enable, :start ]
end

```


Edit the default recipe:

```
   vi recipes/default.rb
```

Update the contents of the `default.rb` recipe with the following contents:


```
include_recipe 'apache::install_apache'

```

Create a `.kitchen.docker.yml` to match the following configuration. 


```
---
driver:
  name: docker

provisioner:
  name: chef_zero

platforms:
  - name: ubuntu-16.04

    driver_config:
      forward:
      - 80:80

suites:
  - name: default
    run_list:
      - recipe[apache::default]
    attributes:


```

Update which configuration kitchen uses by setting the *KITCHEN_LOCAL_YAML* file and then converge your node.

```
$ export KITCHEN_LOCAL_YAML=.kitchen.docker.yml
$ kitchen list
```

Verify that you see 1 instance with a driver Docker.

```
Instance             Driver  Provisioner  Verifier  Transport  Last Action  Last Error
default-ubuntu-1604  Docker  ChefZero     Inspec    Ssh        Converged    <None>
```

Create, and converge the node and login. 

```
$ kitchen converge 
$ kitchen login
```

How do you know if your recipe worked? Kitchen converge finishes without errors, and you have a port up and running. You can check by browsing directly to the node because you have set up port forwarding!

Validate your node has apache up and running:

```
curl localhost

```

## Outcomes

* Use chef generate command to create a cookbook.
* Understand basic kitchen configuration.
* Successfully running Apache on your node.

\pagebreak