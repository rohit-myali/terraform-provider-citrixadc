---
subcategory: "NTP"
---

# Resource: ntpserver

The ntpserver resource is used to create ntpserver.


## Example usage

```hcl
#example with servername
resource "citrixadc_ntpserver" "tf_ntpserver" {
  servername          = "www.example.com"
  minpoll            = 6
  maxpoll            = 10
  preferredntpserver = "YES"

}

#example with serverip
resource "citrixadc_ntpserver" "tf_ntpserver" {
	serverip          = "10.222.74.200"
	minpoll            = 5
	maxpoll            = 9
	preferredntpserver = "NO"
  
  }
```


## Argument Reference

* `serverip` - (Optional) IP address of the NTP server.
* `servername` - (Optional) Fully qualified domain name of the NTP server.
* `autokey` - (Optional) Use the Autokey protocol for key management for this server, with the cryptographic values (for example, symmetric key, host and public certificate files, and sign key) generated by the ntp-keygen utility. To require authentication for communication with the server, you must set either the value of this parameter or the key parameter.
* `key` - (Optional) Key to use for encrypting authentication fields. All packets sent to and received from the server must include authentication fields encrypted by using this key. To require authentication for communication with the server, you must set either the value of this parameter or the autokey parameter.
* `maxpoll` - (Optional) Maximum time after which the NTP server must poll the NTP messages. In seconds, expressed as a power of 2.
* `minpoll` - (Optional) Minimum time after which the NTP server must poll the NTP messages. In seconds, expressed as a power of 2.
* `preferredntpserver` - (Optional) Preferred NTP server. The Citrix ADC chooses this NTP server for time synchronization among a set of correctly operating hosts.



## Attribute Reference

In addition to the arguments, the following attributes are available:

* `id` - The id of the ntpserver. It has the same value as the `serverip` or `servername` attribute.

