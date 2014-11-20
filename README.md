unbound-pmda
============

Performance Metrics Domain Agent (PMDA) for Unbound. Currently adds 140 metrics for unbound. All
total, mem, unwanted, num.rrset, num.answer, histogram and num.query metrics. Missing metrics
that are available in unbound-control, but not yet in this PMDA are per thread stats, time.now,
time.up and time.elapsed.


### Install (assuming PCP is installed, and running)
	mkdir /var/lib/pcp/pmdas/unbound/
	cp Install Remove pmdaunbound.python /var/lib/pcp/pmdas/unbound/
	/var/lib/pcp/pmdas/unbound/Install

### Poll

	% pminfo -fmdtT unbound
	<lists all details about each unbound metric>
	% pminfo unbound
	<lists just the metric names>
	% pmval unbound.num.query.type.A

	metric:    unbound.num.query.type.A
	host:      dns1.example.com
	semantics: cumulative counter (converting to rate)
	units:     count (converting to count / sec)
	samples:   all
            1.188E+04
            1.118E+04
            1.169E+04


But the real value is in logging all these metrics with pmarchive, together with other system
metrics, and being able to replay archives in pmchart, pmwtf, etc.. for analyzing what happened
yesterday evening when customers were complaining about something.
