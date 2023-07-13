# Kusama validator orchestration on AWS

AWS CloudFormation templates to set up Kusama validator on AWS using AWS 
[Elastic Container Service](https://aws.amazon.com/ecs/).

## Considerations

* Validator is placed in a public subnet,
* There's a single public subnet (template has a comment explaining how to add more),
* Only p2p port and prometheus port are open publicly,
* No RPC ports are opened, as the validator needs to be secured,
* Any and all RPC calls need to be executed from within the container (explanation how to attach to container shell 
    provided),
* No public SSH access allowed. AWS 
    [Session Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager.html) is used for 
    security (SSO or AWS Console Access only, both audited)