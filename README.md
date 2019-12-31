This repository contains the datasets used in the [paper](https://dl.acm.org/citation.cfm?id=3365429):

Rebekah Houser, Zhou Li, Chase Cotton, and Haining Wang. 2019. An investigation on information leakage of DNS over TLS. In *Proceedings of the 15th International Conference on Emerging Networking Experiments And Technologies (CoNEXT '19).* ACM, New York, NY, USA, 123-137. DOI: https://doi.org/10.1145/3359989.3365429



### DoT Traces

We collected traces of DoT traffic by visiting the homepage of a set of websites using Firefox (in headless mode, driven by Selenium). DoT traffic was collected between the stub and recursive resolver using tcpdump. Data collection was run between February 2019 and April, 2019, using an EC2 instance in the us-east-1 zone.

Websites are organized into groups of target (pages we attempt to fingerprint), top (pages from the top 150 domains in the Alexa Top Sites list) and random (pages with rank greater than 5000 taken from the Alexa top sites list).

Data is organized into folders according to the following structure:

	<resolver>_<index (index is used if there is more than one dataset for resolver)
		<website group>
			<padding>
				<date-time of capture: YYYY-mm-dd-HH-MM>
					<index of domain>


The name of the domain associated with the website fingerprinted has been replaced with a numerical index unique to that domain in this dataset.

The columns in each file are as follows:

- **Time**: Timestamp (epoch time) that the packet was captured
- **Source**: Source IP address
- **Destination: Destination IP address
- **Length**: Length of the TLS record (bytes)
- **SSL type: **: SSL record type [see RFC 6101](https://tools.ietf.org/html/rfc6101)
