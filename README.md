![Banner](banner.png)

# ds-an-data-masker
A command-line tool that masks sensitive data fields (e.g., credit card numbers, phone numbers) in structured data formats (CSV, JSON) with reversible AES-CTR encryption. Output values are base64 and do not preserve the original format or length, and the same value encrypts differently on each run because a fresh IV is used per value. - Focused on Tools for removing or obfuscating sensitive information from data sets. This includes generating synthetic data to replace real data, redacting specific data fields, and scrambling/masking PII to enable safe sharing and analysis of sensitive data. Intended for use cases like testing and debugging.

## Install
`git clone https://github.com/ShadowStrikeHQ/ds-an-data-masker`

## Usage
`./ds-an-data-masker [params]`

## Parameters
- `-h`: Show help message and exit
- `--unmask`: Unmask data instead of masking.
- `--key`: Encryption key. If not provided, a new key will be generated and printed.
- `--keyfile`: Path to a file containing the encryption key. Overrides --key.

## License
Copyright (c) ShadowStrikeHQ

## Notes
- The output file must not be the input file. A run that names the input as the output is refused at exit 1 before any file is written.
- A run that finds none of the named fields, or that would create no output file (for example a header only or empty CSV), exits 1 with a plain line saying nothing was processed or no output was written. It does not print the completion line.
