# Kyverno Test Setup

<p align="center">
    <img src="./images/gatekeeper.png" alt="Bean on a swing" width="300" height="300">
    <br/>
    You're not getting in (with thoooose shoes)!
</p>

This project provides a test setup for Kyverno policies. It includes the following components:

*   `restrictions.yaml`: Contains the Kyverno policy to be tested.
*   `.kyverno-test/resources.yaml`: Contains example resources used for testing the policy.
*   `.kyverno-test/kyverno-test.yaml`: Contains the Kyverno test configuration that defines the test cases and expected results.

## How to Use

1.  Change into the test directory
2.  Run the Kyverno tests: `kyverno test .`

## Implemented Tests

### Enforce Server Name Indication (SNI) on Port 443

This test enforces that CiliumNetworkPolicies specify `serverNames` when using FQDNs and port 443. This is important for ensuring secure communication and preventing potential security vulnerabilities.

#### Test Cases

*   `good-with-sni-check`: Valid CiliumNetworkPolicy with `serverNames` specified.
*   `bad-no-sni-check`: Invalid CiliumNetworkPolicy missing `serverNames`.
*   `good-with-sni-check-443`: Valid CiliumNetworkPolicy with `serverNames` specified for port 443.
*   `bad-no-sni-check-443`: Invalid CiliumNetworkPolicy missing `serverNames` for port 443.

## More Tests to Come

This project will be expanded to include more Kyverno policy tests in the future.