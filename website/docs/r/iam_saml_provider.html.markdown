---
layout: "aws"
page_title: "AWS: aws_iam_saml_provider"
description: |-
  Provides an IAM SAML provider.
---

# Resource: aws_iam_saml_provider

Provides an IAM SAML provider.

## Example Usage

```hcl
resource "aws_iam_saml_provider" "default" {
  name                   = "myprovider"
  saml_metadata_document = "${file("saml-metadata.xml")}"
}
```

## Argument Reference

The following arguments are supported:

* `name` - (Required) The name of the provider to create.
* `saml_metadata_document` - (Required) An XML document generated by an identity provider that supports SAML 2.0.

## Attributes Reference

In addition to all arguments above, the following attributes are exported:

* `arn` - The ARN assigned by AWS for this provider.
* `valid_until` - The expiration date and time for the SAML provider in RFC1123 format, e.g. `Mon, 02 Jan 2006 15:04:05 MST`.

## Import

IAM SAML Providers can be imported using the `arn`, e.g.

```
$ terraform import aws_iam_saml_provider.default arn:aws:iam::123456789012:saml-provider/SAMLADFS
```
