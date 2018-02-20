# dynamic_iam

`dynamic_iam` allows new IAM roles to be created without having to dedicate huge amounts
of configuration

## Variables

* `dynamic_iam_roles` - a list of dicts. Each dict needs the following keys:
      - `name`: name of the role
      - `policy`: json document for access policy
      - `trust_policy`: json document for trust policy

## Example

```
vars:
  dynamic_iam_roles:
    - name: new-iam-role
      policy: "{{ lookup('template', 'variable_files/iam_policies/new-iam-role-policy.json', convert_data=False) | from_json }}"
      trust_policy: "{{ lookup('template', 'variable_files/iam_policies/new-iam-role-trust-policy.json', convert_data=False) | from_json }}"

roles:
- dynamic_iam
```

