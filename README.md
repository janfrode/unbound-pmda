unbound-pmda
============

PCP PMDA for Unbound. Currently adds almost 100 metrics for unbound. All
total., unwanted., num.rrset., num.answer. and num.query. metrics.


### Install
	mkdir /var/lib/pcp/pmdas/unbound/
	cp Install Remove pmdaunbound.python /var/lib/pcp/pmdas/unbound/
	cd /var/lib/pcp/pmdas/unbound/
	./Install

### Poll

	% pminfo unbound
	<snip>
	unbound.num.query.flags.RD
	unbound.num.query.flags.TC
	unbound.num.query.flags.AA
	unbound.num.query.flags.QR
	unbound.num.query.ipv6
	unbound.num.query.tcp
	unbound.num.query.opcode.QUERY
	unbound.num.query.class.other
	unbound.num.query.class.ANY
	unbound.num.query.class.CLASS240
	unbound.num.query.class.CLASS115
	unbound.num.query.class.CLASS65
	unbound.num.query.class.CLASS6
	<snip>
	% pmval unbound.num.query.type.A

	metric:    unbound.num.query.type.A
	host:      dns1.example.com
	semantics: cumulative counter (converting to rate)
	units:     count (converting to count / sec)
	samples:   all
            1.188E+04
            1.118E+04
            1.169E+04

