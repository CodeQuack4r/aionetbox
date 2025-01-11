# Note
This fork currently under review and only one function was testes "await netbox.dcim.dcim_sites_list()" and some hardcoded flag were set for it to work, library contain parsing issues due to schema architecture change on netbox side, swagger 2.0 -> openApi3

# AIO Netbox

An asyncio netbox library that conforms to any running netbox via it's OpenAPI spec

## Installation

AIONetbox is distributed as a library intended to be included in other asyncio python projects. It has been developed on python 3.6+ though 3.8 is recommended.

```
pip install aionetbox
```

## Usage

```
from aionetbox import AIONetbox

netbox = AIONetbox.from_openapi(
    url='http://localhost:8000',
    api_key='0123abcd'
)

sites = await netbox.dcim.dcim_sites_list()
my_site = await netbox.dcim.dcim_sites_read(id=2)

custom_field_sort = await netbox.dcim.dcim_regions_list(cf_sf_id='identifier')
```

Each module and method map to the swagger definition for netbox (`/api/docs`)

![](https://imgur.com/Mhs4UHz.png)
