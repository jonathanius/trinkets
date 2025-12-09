Temporarily add PyPI and supporting files domain to trusted hosts to install pip-system-certs to allow Windows to rely on local certificates. This can be useful when a proxy issues a self-signed certificate causing PyPI's certificate to show as invalid.

For example, dealing with this error message:
`WARNING: Retrying (Retry(total=4, connect=None, read=None, redirect=None, status=None)) after connection broken by 'SSLError(SSLCertVerificationError(1, '[SSL: 
CERTIFICATE_VERIFY_FAILED] certificate verify failed: self-signed certificate in certificate chain (_ssl.c:1000)'))': /simple/pip/
WARNING: Retrying (Retry(total=3, connect=None, read=None, redirect=None, status=None)) after connection broken by 'SSLError(SSLCertVerificationError(1, '[SSL: 
CERTIFICATE_VERIFY_FAILED] certificate verify failed: self-signed certificate in certificate chain (_ssl.c:1000)'))': /simple/pip/`

> python -m pip config set global.trusted-host "pypi.org files.pythonhosted.org"

> python -m pip install --upgrade pip

> python -m pip install pip-system-certs

> python -m pip config unset global.trusted-host
