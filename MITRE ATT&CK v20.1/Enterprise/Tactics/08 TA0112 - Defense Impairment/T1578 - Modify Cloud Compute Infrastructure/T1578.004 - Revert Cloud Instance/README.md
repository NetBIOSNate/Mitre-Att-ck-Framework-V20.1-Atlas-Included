# T1578.004 - Revert Cloud Instance

[Enterprise](../../../../README.md) / [Defense Impairment](../../README.md) / [T1578 - Modify Cloud Compute Infrastructure](../README.md)

An adversary may revert changes made to a cloud instance after they have performed malicious activities in attempt to evade detection and remove evidence of their presence. In highly virtualized environments, such as cloud-based infrastructure, this may be accomplished by restoring virtual machine (VM) or data storage snapshots through the cloud management dashboard or cloud APIs.

Another variation of this technique is to utilize temporary storage attached to the compute instance. Most cloud providers provide various types of storage including persistent, local, and/or ephemeral, with the ephemeral types often reset upon stop/restart of the VM.(Citation: Tech Republic - Restore AWS Snapshots)(Citation: Google - Restore Cloud Snapshot)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1578/004)

**Tactics**  [Defense Impairment](../../README.md)

**Platforms**  [IaaS](../../../../Platforms/IaaS.md)

## Detection strategies

- [DET0337 - Detection Strategy for Modify Cloud Compute Infrastructure: Revert Cloud Instance](../../../../Defenses/Detection%20Strategies/DET0337%20-%20Detection%20Strategy%20for%20Modify%20Cloud%20Compute%20Infrastructure%20-%20Revert%20Cloud%20Instance.md)

## Sources

- [Google - Restore Cloud Snapshot](https://cloud.google.com/compute/docs/disks/restore-and-delete-snapshots)
- [Tech Republic - Restore AWS Snapshots](https://www.techrepublic.com/blog/the-enterprise-cloud/backing-up-and-restoring-snapshots-on-amazon-ec2-machines/)
