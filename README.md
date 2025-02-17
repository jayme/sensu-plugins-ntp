## sensu-plugins-ntp

[ ![Build Status](https://travis-ci.org/sensu-plugins/sensu-plugins-ntp.svg?branch=master)](https://travis-ci.org/sensu-plugins/sensu-plugins-ntp)
[![Gem Version](https://badge.fury.io/rb/sensu-plugins-ntp.svg)](http://badge.fury.io/rb/sensu-plugins-ntp)
[![Code Climate](https://codeclimate.com/github/sensu-plugins/sensu-plugins-ntp/badges/gpa.svg)](https://codeclimate.com/github/sensu-plugins/sensu-plugins-ntp)
[![Test Coverage](https://codeclimate.com/github/sensu-plugins/sensu-plugins-ntp/badges/coverage.svg)](https://codeclimate.com/github/sensu-plugins/sensu-plugins-ntp)
[![Dependency Status](https://gemnasium.com/sensu-plugins/sensu-plugins-ntp.svg)](https://gemnasium.com/sensu-plugins/sensu-plugins-ntp)
[![Sensu Bonsai Asset](https://img.shields.io/badge/Bonsai-Download%20Me-brightgreen.svg?colorB=89C967&logo=sensu)](https://bonsai.sensu.io/assets/sensu-plugins/sensu-plugins-ntp)

## Sensu Asset  
  The Sensu assets packaged from this repository are built against the Sensu ruby runtime environment. When using these assets as part of a Sensu Go resource (check, mutator or handler), make sure you include the corresponding Sensu ruby runtime asset in the list of assets needed by the resource.  The current ruby-runtime assets can be found [here](https://bonsai.sensu.io/assets/sensu/sensu-ruby-runtime) in the [Bonsai Asset Index](bonsai.sensu.io).


## Functionality

Provides plugins for checking and measuring Network Time Protocol (NTP)
servers.

## Usage

### check-ntp.rb

Check the synchronization state of the local NTP server.

**parameters:**

- `warn`: Maximum offset in ms for warning state (default: `10`)
- `crit`: Maximum offset in ms for critical state (default: `100`)
- `stratum`: Maximum stratum value (default: `15`)
- `unsynced_status`: Default status when unsynced (default: `UNKNOWN`)


### metrics-ntpdate.rb

Get metrics from ntpdate.

**parameters:**

- `server`: Comma separated list of NTP server(s) to measure (default:
  `localhost`)
- `scheme`: Prefix for metrics (default: `hostname`)

**values:**

- `offset`: Time difference between server and source (unit: ms)
- `delay`: Roundtrip time from server to source (unit: ms)

### metrics-ntpstats.rb

Get metrics from ntpstats.

**parameters:**

- `host`: Target host (default: `localhost`)
- `scheme`: Prefix for metrics (default: `hostname`)

**values:**

Descriptions taken from https://www.eecis.udel.edu/~mills/ntp/html/ntpq.html.

- `clk_jitter`: Clock jitter
- `clk_wander`: Clock frequency wander
- `frequency`: Frequency offset relative to hardware clock
- `mintc`: Minimum time constant
- `offset`: Combined offset of server relative to this host
- `stratum`: Stratum
- `sys_jitter`: Combined system jitter
- `tc`: Time constant and poll exponent

## Installation

```plain
sensu-install --plugin sensu-plugins-ntp
```
