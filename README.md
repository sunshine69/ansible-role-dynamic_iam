# dynamic_iam

`dynamic_iam` allows new IAM roles to be created without having to dedicate huge amounts
of configuration

## Variables

* `dynamic_iam_roles` - a list of dicts. Each dict needs the following keys:
      - `name`: name of the role
      - `policy`: path to the template to use for the policy json document
      - `trust_policy`: path to the template to use for the trust policy json document

## Example

```
vars:
  dynamic_iam_roles:
    - name: new-iam-role
      policy: "{{ inventory_dir }}/../variable_files/iam_policies/new-iam-role.json"
      trust_policy: "{{ inventory_dir }}/../variable_files/iam_policies/new-iam-role-trust-policy.json"

roles:
- dynamic_iam
```

