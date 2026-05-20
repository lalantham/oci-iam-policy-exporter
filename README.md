# OCI IAM Policy Exporter

Fetches all active IAM policies across every compartment in an OCI tenancy and exports them to a structured Excel file for auditing or documentation.

## Output

`oci_policies.xlsx` with columns:

| Policy Name | Policy ID | Compartment OCID | Policy Statements |
|---|---|---|---|

## Prerequisites

- Python 3.x
- OCI CLI installed and configured (`~/.oci/config`)
- Permissions to read compartments and policies

## Setup

```bash
pip install -r requirements.txt
```

## Usage

```bash
python export_policies.py
```

The script will:
1. Read your tenancy OCID from `~/.oci/config`
2. Recursively fetch all active compartments
3. Fetch all active policies from each compartment
4. Save results to `oci_policies.xlsx`

## IAM permissions required

```
Allow group <your-group> to read compartments in tenancy
Allow group <your-group> to read policies in tenancy
```
