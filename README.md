# Lock Plugin Metadata

This repository contains metadata about the plugin starter packages which can be 
used as templates for new projects in Lock. Lock is in development.

It's very early stage, these are initial ideas, so the format of the metadata is likely to change.

### What is this?

The basic idea is that [Lock](https://github.com/spoonboy-io/lock) will poll this repository for data about repositories
which contain morpheus plugins: templates, starters, maybe even production versions.

Lock will create projects by cloning a repository and checking out a specific tag in the cloned repository - or default to head.

All the tag info will be found by cloning, but format inconsistency is likely. The metadata here is limited but aims to inform Lock how to interprete the branch/tag/release naming system
used in each repository, and indeed the availability of it, when displaying repositories which can be used as starters.

Metadata is "currently" YAML syntax, and this is the "current" configuration format: 

```yaml
---
- plugin:
    ## category: approvals, cypher, dns, tab, ipam, task, report, cloud, or backup
    category: a category
    description: description of the plugin/repo
    url: url from which the repo can be cloned
    
    ## tags are for additional metadata not tags from the repository
    tags: tag1,tag2,tag3
    
    ## these below configuration options are shown with their defaults
    ## unless a different value is specified they may be omitted
    versioning:
      semantic: true 
      semanticPrefix: v
      morpheus: true
      morpheusPrefix: morpheus
    disabled: false
```

The metadata file `lock.yaml` can be viewed [here](https://github.com/spoonboy-io/lock-plugin-metadata/blob/main/lock.yaml). 

### Contributions

Once the format is finalised and the Lock application is version 1, contributions will be accepted.
