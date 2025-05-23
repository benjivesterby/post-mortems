# A List of Post-mortems!

## Table of Contents

 - **[Config Errors](#config-errors)**
 - **[Hardware/Power Failures](#hardwarepower-failures)**
 - **[Conflicts](#conflicts)**
 - **[Time](#time)**
 - **[Database](#database)**
 - **[Uncategorized](#uncategorized)**
 - **[Other lists of postmortems](#other-lists-of-postmortems)**
 - **[Analysis](#analysis)**
 - **[Contributors](#contributors)**

<br/><br/>

## Config Errors

[Allegro](https://allegro.tech/2018/08/postmortem-why-allegro-went-down.html). E-commerce site went down after a sudden traffic spike caused by a marketing campaign. The outage was caused by a configuration error in cluster resource management which prevented more service instances from starting even though hardware resources were available.

[Cloudflare](https://web.archive.org/web/20211006135542/https://blog.cloudflare.com/todays-outage-post-mortem-82515/). A bad config (router rule) caused all of their edge routers to crash, taking down all of Cloudflare.

[Cloudflare](https://web.archive.org/web/20211016040522/https://blog.cloudflare.com/cloudflare-outage-on-july-17-2020/). During a maintenance of their private backbone network, an engineer made a typo in the Atlanta datacenter network configuration, causing all traffic coming from America and Europe flowing to this only datacenter, crushing it.

[Cloudflare](https://web.archive.org/web/20220621124002/https://blog.cloudflare.com/cloudflare-outage-on-june-21-2022/). An incorrect ordering of the disabled BGP advertised prefixes caused malfunction on 19 datacenters.

[Cloudflare](https://web.archive.org/web/20221112015610/https://blog.cloudflare.com/partial-cloudflare-outage-on-october-25-2022/). A change to our Tiered Cache system caused some requests to fail for users with status code 530. The impact lasted for almost six hours in total. We estimate that about 5% of all requests failed at peak. Because of the complexity of our system and a blind spot in our tests, we did not spot this when the change was released to our test environment.

[Cloudflare](https://blog.cloudflare.com/cloudflare-incident-on-january-24th-2023/). Several Cloudflare services became unavailable for 121 minutes on January 24, 2023 due to an error releasing code that manages service tokens. The incident degraded a wide range of Cloudflare products including aspects of our Workers platform, our Zero Trust solution, and control plane functions in our content delivery network (CDN).

[Cloudflare](https://blog.cloudflare.com/1-1-1-1-lookup-failures-on-october-4th-2023/). On 4 October 2023, Cloudflare experienced DNS resolution problems starting at 07:00 UTC and ending at 11:00 UTC. Some users of 1.1.1.1 or products like WARP, Zero Trust, or third party DNS resolvers which use 1.1.1.1 may have received SERVFAIL DNS responses to valid queries. We’re very sorry for this outage. This outage was an internal software error and not the result of an attack. In this blog, we’re going to talk about what the failure was, why it occurred, and what we’re doing to make sure this doesn’t happen again.

[DataDog](https://www.datadoghq.com/blog/2020-09-25-infrastructure-connectivity-issue/). A bad service discovery config in one of the clients brought down service discovery globally when a dependent client went down.

[Enom](https://enomstatus.com/incidents/03q064h6rb7x). On January 15, 2022, at 9:00 AM ET, Tucows’ engineering team began planned maintenance work to migrate the Enom platform to a new cloud infrastructure. Due to the complexity of the cutover, the team encountered many issues resulting in continuous delays. The maintenance window was extended multiple times to address issues related to data replication, network routing, and DNS resolution issues impacting website accessibility and email delivery.

[Etsy](https://web.archive.org/web/20211201033341/https://codeascraft.com/2012/01/23/solr-bittorrent-index-replication/). Sending multicast traffic without properly configuring switches caused an Etsy global outage.

[Facebook](https://engineering.fb.com/2021/10/05/networking-traffic/outage-details/). Configuration changes to Facebook's backbone routers caused a global outage of all Facebook properties and internal tools.

[Facebook](https://blog.thousandeyes.com/facebook-outage-deep-dive/). A bad config took down both Facebook and Instagram.

[Firefox](https://web.archive.org/web/20250314111052/https://hacks.mozilla.org/2022/02/retrospective-and-technical-details-on-the-recent-firefox-outage/). On January 13th, 2022, a specific code path in Firefox's network stack triggered a problem in the HTTP/3 protocol implementation. This blocked network communication and made Firefox unresponsive, unable to load web content for nearly two hours.

[GoCardless](https://gocardless.com/blog/incident-review-api-and-dashboard-outage-on-10th-october/). A bad config combined with an uncommon set of failures led to an outage of a database cluster, taking the API and Dashboard offline.

[Google](https://cloud.google.com/blog/products/infrastructure/details-of-google-cloud-gcve-incident). Initial GCVE provisioning was performed with a legacy option, which lead to a 'fixed term' contract with automatic deletion at the end of that period.

[Google](https://status.cloud.google.com/incident/compute/16007). A bad config (autogenerated) removed all Google Compute Engine IP blocks from BGP announcements.

[Google](https://googleblog.blogspot.com/2014/01/todays-outage-for-several-google.html). A bad config (autogenerated) took down most Google services.

[Google](https://web.archive.org/web/20151008061104/http://code.google.com/p/chromium/issues/detail?id=165171). A bad config caused a quota service to fail, which caused multiple services to fail (including gmail).

[Google](https://googleblog.blogspot.com/2009/01/this-site-may-harm-your-computer-on.html). `/` was checked into the URL blacklist, causing every URL to show a warning.

[Google](https://status.cloud.google.com/incident/compute/17007#5659118702428160). A bug in configuration roll-out to a load balancer lead to increased error rates for 22 minutes.

[Google](https://status.cloud.google.com/incident/storage/19002). A configuration change intended to address an uptick in demand for metadata storage, which overloaded part of the blob lookup system, which caused a cascading failure with user-visible service impact to Gmail, Google Photos, Google Drive, and other GCP services dependent on blob storage.

[Google](https://status.cloud.google.com/incident/cloud-networking/19009). Two misconfigurations, plus a software bug, caused a massive Google Cloud Network failure on the US East Coast.

[Google](https://status.cloud.google.com/incidents/1xkAB1KmLrh5g3v9ZEZ7). Google’s Front End load balancing service experienced failures resulting in impact to several downstream Google Cloud services in Europe. From preliminary analysis, the root cause of the issue was caused by a new infrastructure feature triggering a latent issue within internal network load balancer code.

[Google](https://status.cloud.google.com/incidents/6PM5mNd43NbMqjCZ5REh). Google Cloud Networking experienced issues with Google Cloud Load Balancing (GCLB) service resulting in impact to several downstream Google Cloud services. Impacted customers observed Google 404 errors on their websites. From preliminary analysis, the root cause of the issue was a latent bug in a network configuration service which was triggered during routine system operation.

[Google](https://status.cloud.google.com/incidents/vLsxuKoRvykNHW3nnhsJ). Google Cloud Networking experienced reduced capacity for lower priority traffic such as batch, streaming and transfer operations from 19:30 US/Pacific on Thursday, 14 July 2022, through 15:02 US/Pacific on Friday, 15 July 2022. High-priority user-facing traffic was not affected. This service disruption resulted from an issue encountered during a combination of repair work and a routine network software upgrade rollout. Due to the nature of the disruption and resilience capabilities of Google Cloud products, the impacted regions and individual impact windows varied substantially.

[Heroku](https://status.heroku.com/incidents/1091). An automated remote configuration change did not propagate fully. Web dynos could not be started.

[Heroku](https://blog.heroku.com/how-i-broke-git-push-heroku-main). An incorrect deployment process caused new config variables not to be used when the code required them.

[Keepthescore](https://web.archive.org/web/20201101133510/https://keepthescore.co/blog/posts/deleting_the_production_database/). Engineers deleted the production database by accident. Database is a managed database from DigitalOcean with backups once a day. 30 minutes after the disaster, it went back online, however 7 hours of scoreboard data was gone forever.

[Microsoft](https://azure.microsoft.com/en-us/blog/update-on-azure-storage-service-interruption/). A bad config took down Azure storage.

[NPM](https://blog.npmjs.org/post/74949623024/2014-01-28-outage-postmortem.html). Fastly configuration change caused backend routing issue. To be exact, the issue is that we were setting the req.backend in a vcl_fetch function, and then calling restart to re-parse the rules. However, calling restart will reset the req.backend to the first backed in the list, which in this case happened to be Manta, rather than the load balanced CouchDB servers.

[OWASA](https://web.archive.org/web/20210226170650/https://indyweek.com/news/archives/human-error-caused-owasa-fluoride-overdose-owasa-sorry/). The wrong push of a button lead to a water treatment plant shutting down due to too high levels of fluoride.

[PagerDuty](https://status.pagerduty.com/incidents/vbp7ht2647l8). On December 15th, 2021 at 00:17 UTC, we deployed a DNS configuration change in PagerDuty’s infrastructure that impacted our container orchestration cluster. The change contained a defect, that we did not detect in our testing environments, which immediately caused all services running in the container orchestration cluster to be unable to resolve DNS.

[Razorpay](https://razorpay.com/blog/day-of-rds-multi-az-failover/). A RDS hardware failure highlighted an incorrect MySQL configuration which resulted in major data loss in a financial system.

[rust-lang](https://blog.rust-lang.org/inside-rust/2023/02/08/dns-outage-portmortem.html). On Wednesday, 2023-01-25 at 09:15 UTC, we deployed changes to the production infrastructure for crates.io. During the deployment, the DNS record for static.crates.io failed to resolve for an estimated time of 10-15 minutes. It was due to the fact that both certificates and DNS records were re-created during the downtime.

[rust-lang](https://blog.rust-lang.org/inside-rust/2023/07/21/crates-io-postmortem.html). On 2023-07-20 between 12:17 and 12:30 UTC all crate downloads from crates.io were broken due to a deployment that contained a bug in the download URL generation. During this time we had an average of 4.71K requests per second to crates.io, resulting in about 3.7M failed requests, including the retry attempts from cargo.

[Stack Overflow](https://web.archive.org/web/20201020103424/https://stackstatus.net/post/96025967369/outage-post-mortem-august-25th-2014). A bad firewall config blocked stackexchange/stackoverflow.

[Sentry](https://blog.sentry.io/2016/06/14/security-incident-june-12-2016). Wrong Amazon S3 settings on backups lead to data leak.

[TravisCI](https://www.traviscistatus.com/incidents/khzk8bg4p9sy). A configuration issue (incomplete password rotation) led to "leaking" VMs, leading to elevated build queue times.

[TravisCI](https://web.archive.org/web/20221220114914/https://blog.travis-ci.com/2016-09-30-the-day-we-deleted-our-vm-images/). A configuration issue (automated age-based Google Compute Engine VM image cleanup job) caused stable base VM images to be deleted.

[TravisCI](https://www.traviscistatus.com/incidents/sxrh0l46czqn). A configuration change made builds start to fail. Manual rollback broke.

[TravisCI](https://www.traviscistatus.com/incidents/z2b3lz2kwcfp). Accidental environment variable made tests truncate production database.

[TUI](https://assets.publishing.service.gov.uk/media/604f423be90e077fdf88493f/Boeing_737-8K5_G-TAWG_04-21.pdf). Prior to the incident flight the reservation system from which the load sheet was produced had been upgraded. A fault in the system caused female passengers checked in with title ‘Miss’ to be counted as children. The system allocated them a child’s standard weight of 35 kg as opposed to the correct female standard weight of 69 kg. Consequently, with 38 females checked in incorrectly and misidentified as children, the G-TAWG takeoff mass from the load sheet was 1,244 kg below the actual mass of the aircraft.

[Turso](https://blog.turso.tech/incident-2023-12-04-data-leak-and-loss-in-some-free-tier-databases-7cba5bc7). Incorrectly configured DB backup identifiers led to data leaks for free tier customers, and the subsequent fix resulted in possible data loss.

[Valve](https://blog.thousandeyes.com/steam-outage-monitor-data-center-connectivity/). Although there's no official postmortem, it looks like a bad BGP config severed Valve's connection to Level 3, Telia, and Abovenet/Zayo, which resulted in a global Steam outage.

## Hardware/Power Failures

[Amazon](https://aws.amazon.com/message/2329B7/). An unknown event caused a transformer to fail. One of the PLCs that checks that generator power is in phase failed for an unknown reason, which prevented a set of backup generators from coming online. This affected EC2, EBS, and RDS in EU West.

[Amazon](https://aws.amazon.com/message/67457/). Bad weather caused power failures throughout AWS US East. A single backup generator failed to deliver stable power when power switched over to backup and the generator was loaded. This is despite having passed a load tests two months earlier, and passing weekly power-on tests.

[Amazon](https://aws.amazon.com/message/4372T8/). At 10:25pm PDT on June 4, loss of power at an AWS Sydney facility resulting from severe weather in that area lead to disruption to a significant number of instances in an Availability Zone. Due to the signature of the power loss, power  isolation breakers did not engage, resulting in backup energy reserves draining into the degraded power grid.

[ARPANET](https://datatracker.ietf.org/doc/html/rfc789.html). A malfunctioning IMP ([Interface Message Processor](https://en.wikipedia.org/wiki/Interface_Message_Processor)) corrupted routing data, software recomputed checksums propagating bad data with good checksums, incorrect sequence numbers caused buffers to fill, full buffers caused loss of keepalive packets and nodes took themselves off the network. From 1980.

[Cloudflare](https://web.archive.org/web/20211015231917/https://blog.cloudflare.com/a-byzantine-failure-in-the-real-world/). A partial switch misbehavior caused a cascading Byzantine failure which impacted the availability of the API and dashboard for six hours and 33 minutes.

[Cloudflare](https://blog.cloudflare.com/post-mortem-on-cloudflare-control-plane-and-analytics-outage/). Flexential Data Center Power Failure. This post outlines the events that caused this incident.

[FirstEnergy / General Electric](https://en.wikipedia.org/wiki/Northeast_blackout_of_2003). FirstEnergy had a local failure when some transmission lines hit untrimmed foliage. The normal process is to have an alarm go off, which causes human operators to re-distribute power. But the GE system that was monitoring this had a bug which prevented the alarm from getting triggered, which eventually caused a cascading failure that eventually affected 55 million people.

[GitHub](https://github.com/blog/2106-january-28th-incident-report). On January 28th, 2016 GitHub experienced a disruption in the power at their primary datacenter.

[Google](https://status.cloud.google.com/incident/compute/15056#5719570367119360). Successive lightning strikes on their European datacenter (europe-west1-b) caused loss of power to Google Compute Engine storage systems within that region. I/O errors were observed on a subset of Standard Persistent Disks (HDDs) and permanent data loss was observed on a small fraction of those.

[Google](https://status.cloud.google.com/incidents/fmEL9i2fArADKawkZAa2). On Tuesday, 19 July 2022 at 06:33 US/Pacific, a simultaneous failure of multiple, redundant cooling systems in one of the data centers that hosts the zone europe-west2-a impacted multiple Google Cloud services. This resulted in some customers experiencing service unavailability for impacted products.

[PythonAnywhere](https://blog.pythonanywhere.com/189/). A storage volume failure on one of storage servers caused a number of outages, starting with PythonAnywhere site and also with our users’ programs (including websites) that were dependent on that volume, and later spreading to other hosted sites.

[Sun](https://www.forbes.com/forbes/2000/1113/6613068a.html#6d1bdc036162). Sun famously didn't include ECC in a couple generations of server parts. This resulted in data corruption and crashing. Following Sun's typical MO, they made customers that reported a bug sign an NDA before explaining the issue.

## Conflicts

[CCP Games](https://community.eveonline.com/news/dev-blogs/about-the-boot.ini-issue/). A typo and a name conflict caused the installer to sometimes delete the *boot.ini* file on installation of an expansion for *EVE Online* - with [consequences.](https://www.youtube.com/watch?v=msXRFJ2ar_E)

[GitHub](https://blog.github.com/2018-10-30-oct21-post-incident-analysis/). A 43 second network partition during maintenance caused MySQL master failover, but the new master didn't have several seconds of writes propogated to it because of cross-continent latency.  24+ hours of restoration work to maintain data integrity.

[GoCardless](https://gocardless.com/blog/zero-downtime-postgres-migrations-the-hard-parts/). All queries on a critical PostgreSQL table were blocked by the combination of an extremely fast database migration and a long-running read query, causing 15 seconds of downtime.

[Google](https://status.cloud.google.com/incident/compute/17003#5660850647990272). Many changes to a rarely modified load balancer were applied through a very slow code path. This froze all public addressing changes for ~2 hours.

[Google](https://status.cloud.google.com/incidents/eo76pxZiDgWVz4z3kmUv). A failure of a component on a fiber path from one of the central US gateway campuses in Google’s production backbone led to a decrease in available network bandwidth between the gateway and multiple edge locations, causing packet loss while the backbone automatically moved traffic onto remaining paths.

[Knight Capital](https://dougseven.com/2014/04/17/knightmare-a-devops-cautionary-tale/). A combination of conflicting deployed versions and re-using a previously used bit caused a $460M loss. See also a [longer write-up](https://www.henricodolfing.com/2019/06/project-failure-case-study-knight-capital.html).

[WebKit code repository](https://web.archive.org/web/20210306015541/https://digital.ai/catalyst-blog/subversion-sha1-collision-problem-statement-prevention-and-remediation-options). The WebKit repository, a Subversion repository configured to use deduplication, became unavailable after two files with the same SHA-1 hash were checked in as test data, with the intention of implementing a safety check for collisions. The two files had different md5 sums and so a checkout would fail a consistency check. For context, the first public SHA-1 hash collision had very recently been announced, with an example of two colliding files.

## Time

[Azure](https://azure.microsoft.com/en-us/blog/summary-of-windows-azure-service-disruption-on-feb-29th-2012/). Certificates that were valid for one year were created. Instead of using an appropriate library, someone wrote code that computed one year to be the current date plus one year. On February 29th 2012, this resulted in the creation of certificates with an expiration date of February 29th 2013, which were rejected because of the invalid date. This caused an Azure global outage that lasted for most of a day.

[Cloudflare](https://web.archive.org/web/20211104160742/https://blog.cloudflare.com/how-and-why-the-leap-second-affected-cloudflare-dns/). Backwards time flow from tracking [the 27th leap second on 2016-12-31T23:59:60Z](https://hpiers.obspm.fr/iers/bul/bulc/bulletinc.52) caused the weighted round-robin selection of DNS resolvers (RRDNS) to panic and fail on some CNAME lookups.  Go's `time.Now()` was incorrectly assumed to be monotonic; this injected negative values into calls to `rand.Int63n()`, which panics in that case.

[Linux](https://web.archive.org/web/20220427012208/https://lkml.org/lkml/2009/1/2/373). Leap second code was called from the timer interrupt handler, which held `xtime_lock`. That code did a `printk` to log the leap second. `printk` wakes up `klogd`, which can sometimes try to get the time, which waits on `xtime_lock`, causing a deadlock.

[Linux](https://web.archive.org/web/20220320100036/https://lkml.org/lkml/2012/7/1/203). When a leap second occurred, `CLOCK_REALTIME` was rewound by one second. This was not done via a mechanism that would update `hrtimer base.offset`. This meant that when a timer interrupt happened, TIMER_ABSTIME CLOCK_REALTIME timers got expired one second early, including timers set for less than one second. This caused applications that used sleep for less than one second in a loop to spinwait without sleeping, causing high load on many systems. This caused a large number of web services to go down in 2012.

[Mozilla](https://web.archive.org/web/20250303152906/https://hacks.mozilla.org/2019/07/add-ons-outage-post-mortem-result/). Most Firefox add-ons stopped working around May 4th 2019 when a certificate expired. Firefox requires a valid certificate chain to prevent malware. About nine hours later, Mozilla pushed a privileged add-on that injected a valid certificate into Firefox's certificate store, creating a valid chain and unblocking add-ons. This disabled effectively all add-ons, about 15,000, and the resolution took approximately 15-21 hours for most users. Some user data was lost. Previously Mozilla [posted](https://web.archive.org/web/20250408175304/https://hacks.mozilla.org/2019/05/technical-details-on-the-recent-firefox-add-on-outage/) about the technical details.

## Database

[Github](https://github.blog/2021-12-01-github-availability-report-november-2021/). Github platform encountered a novel failure mode when processing a schema migration on a large MySQL table. Schema migrations are a common task at GitHub and often take weeks to complete. The final step in a migration is to perform a rename to move the updated table into the correct place. During the final step of this migration a significant portion of our MySQL read replicas entered a semaphore deadlock. Our MySQL clusters consist of a primary node for write traffic, multiple read replicas for production traffic, and several replicas that serve internal read traffic for backup and analytics purposes. The read replicas that hit the deadlock entered a crash-recovery state causing an increased load on healthy read replicas. Due to the cascading nature of this scenario, there were not enough active read replicas to handle production requests which impacted the availability of core GitHub services.

[Heroku](https://status.heroku.com/incidents/2558). At 15:05 UTC on June 8, 2023, a database error occurred where a foreign key used a smaller data type than the primary key that it referenced. This error caused an overflow when the primary key exceeded the allowable value, resulting in an inability to create new authorizations within Heroku. This error also prevented customers from creating new deployments. The oncall operations then triggered the Heroku API full outage.

## Uncategorized

[Allegro](https://allegro.tech/2015/01/allegro-cast-post-mortem.html). The [Allegro](https://web.archive.org/web/20211204232004/https://allegro.pl/) platform suffered a failure of a subsystem responsible for asynchronous distributed task processing. The problem affected many areas, e.g. features such as purchasing numerous offers via cart and bulk offer editing (including price list editing) did not work at all. Moreover, it partially failed to send daily newsletter with new offers. Also some parts of internal administration panel were affected.

[Amazon](https://aws.amazon.com/message/41926/). Human error. On February 28th 2017 9:37AM PST, the Amazon S3 team was debugging a minor issue. Despite using an established playbook, one of the commands intending to remove a small number of servers was issued with a typo, inadvertently causing a larger set of servers to be removed. These servers supported critical S3 systems. As a result, dependent systems required a full restart to correctly operate, and the system underwent widespread outages for US-EAST-1 (Northern Virginia) until final resolution at 1:54PM PST. Since Amazon's own services such as EC2 and EBS rely on S3 as well, it caused a vast cascading failure which affected hundreds of companies.

[Amazon](https://web.archive.org/web/20220403060108/https://status.aws.amazon.com/s3-20080720.html). Message corruption caused the distributed server state function to overwhelm resources on the S3 request processing fleet.

[Amazon](https://aws.amazon.com/message/65648/). Human error during a routine networking upgrade led to a resource crunch, exacerbated by software bugs, that ultimately resulted in an outage across all US East Availability Zones as well as a loss of 0.07% of volumes.

[Amazon](https://aws.amazon.com/message/680342/). Inability to contact a data collection server triggered a latent memory leak bug in the reporting agent on the storage servers. And there is no graceful degradation handling, thus the reporting agent continuously contacted the collection server in a way that slowly consumed system memory. Also the monitoring system failed to alarm this EBS server's memory leak, also EBS servers generally make very dynamic use of all memory. By Monday morning, the rate of memory loss became quite high and confused enough memory on the affected storage servers which cannot keep with the request handling process. This error got further severed by the inability to do the failover, which resulted in the outage.

[Amazon](https://aws.amazon.com/message/680587/). Elastic Load Balancer ran into problems when "a maintenance process that was inadvertently run against the production ELB state data".

[Amazon](https://aws.amazon.com/message/5467D2/). A "network disruption" caused metadata services to experience load that caused response times to exceed timeout values, causing storage nodes to take themselves down. Nodes that took themselves down continued to retry, ensuring that load on metadata services couldn't decrease.

[Amazon](https://aws.amazon.com/message/11201/). Scaling the front-end cache fleet for Kinesis caused all of the servers in the fleet to exceed the maximum number of threads allowed by an operating system configuration. Multiple critical downstream services affected, from Cognito to Lambda to CloudWatch.

[Amazon](https://aws.amazon.com/message/12721/). At 7:30 AM PST, an automated activity to scale capacity of one of the AWS services hosted in the main AWS network triggered an unexpected behavior from a large number of clients inside the internal network. This resulted in a large surge of connection activity that overwhelmed the networking devices between the internal network and the main AWS network, resulting in delays for communication between these networks. These delays increased latency and errors for services communicating between these networks, resulting in even more connection attempts and retries. This led to persistent congestion and performance issues on the devices connecting the two networks.

[AppNexus](https://medium.com/xandr-tech/2013-09-17-outage-postmortem-586b19ae4307). A double free revealed by a database update caused all "impression bus" servers to crash simultaneously. This wasn't caught in staging and made it into production because a time delay is required to trigger the bug, and the staging period didn't have a built-in delay.

[AT&T](https://users.csc.calpoly.edu/~jdalbey/SWE/Papers/att_collapse.html). A bad line of C code introduced a race hazard which in due course collapsed the phone network. After a planned outage, the quickfire resumption messages triggered the race,  causing more reboots which retriggered the problem. "The problem repeated iteratively throughout the 114 switches in the network, blocking over 50 million calls in the nine hours it took to stabilize the system." From 1990.

[Atlassian](https://www.atlassian.com/engineering/post-incident-review-april-2022-outage). On Tuesday, April 5th, 2022, starting at 7:38 UTC, 775 Atlassian customers lost access to their Atlassian products. The outage spanned up to 14 days for a subset of these customers, with the first set of customers being restored on April 8th and all customer sites progressively restored by April 18th.

[Basecamp](https://signalvnoise.com/posts/3729-basecamp-network-attack-postmortem), [see also](https://signalvnoise.com/posts/3728-basecamp-was-under-network-attack-this-morning). Basecamp's network was under a DDoS attack during a 100-minute window on March 24, 2014.

[Basecamp](https://web.archive.org/web/20220529044310/https://m.signalvnoise.com/postmortem-on-the-read-only-outage-of-basecamp-on-november-9th-2018/), [see also](https://web.archive.org/web/20220530044506/https://m.signalvnoise.com/update-on-basecamp-3-being-stuck-in-read-only-as-of-nov-8-922am-cst/). In November 2018 a database hit the integer limit, leaving the service in read-only mode.

[BBC Online](https://www.bbc.co.uk/blogs/internet/entries/a37b0470-47d4-3991-82bb-a7d5b8803771). In July 2014, BBC Online experienced a very long outage of several of its popular online services including the BBC iPlayer. When the database backend was overloaded, it had started to throttle requests from various services. Services that hadn't cached the database responses locally began timing out and eventually failed completely.

[Bintray](https://web.archive.org/web/20210421222929/https://status.bintray.com/incidents/w4dfr0rpznkt). In July 2017 several malicious Maven packages were included in JCenter with an impersonation attack. Those packages lived in JCenter for over a year and supposedly affected several Android apps that resulted in having malware code injected by those dependencies from JCenter.

[Bitly](https://blog.bitly.com/post/85260908544/more-detail). Hosted source code repo contained credentials granting access to bitly backups, including hashed passwords.

[BrowserStack](https://www.browserstack.com/attack-and-downtime-on-9-November). An old prototype machine with the [Shellshock](https://en.wikipedia.org/wiki/Shellshock_(software_bug)) vulnerability still active had secret keys on it which ultimately led to a security breach of the Production system.

[Buildkite](https://building.buildkite.com/outage-post-mortem-for-august-23rd-82b619a3679b). Database capacity downgrade in an attempt to minimise AWS spend resulted in lack of capacity to support Buildkite customers at peak, leading to cascading collapse of dependent servers.

[Bungie](https://web.archive.org/web/20230504222953/https://www.bungie.net/en/News/Article/48723). Side effects of a bug fix for wrong timestamps causes data loss; server misconfiguration for the hotfix causes the data loss to reappear in several servers in a following update.

[CCP Games](https://community.eveonline.com/news/dev-blogs/behind-the-scenes-of-a-long-eve-online-downtime/). A problematic logging channel caused cluster nodes dying off during the cluster start sequence after rolling out a new game patch.

[CCP Games](https://community.eveonline.com/news/dev-blogs/sleeping-beauty/). Documents a Stackless Python memory reuse bug that took years to track down.

[Chef.io](https://www.chef.io/blog/2014/07/10/supermarket-intermittent-unresponsiveness-postmortem/). The recipe community site Supermarket crashed two hours after launch due to intermittent unresponsiveness and increased latency. One of the main reasons for failure identified in the post mortem was very low health check timeouts.

[CircleCI](https://circleci.statuspage.io/incidents/hr0mm9xmm3x6). A GitHub outage and recovery caused an unexpectedly large incoming load. For reasons that aren't specified, a large load causes CircleCI's queue system to slow down, in this case to handling one transaction per minute.

[CircleCI](https://circleci.com/blog/jan-4-2023-incident-report/). By January 4, 2023, our internal investigation had determined the scope of the intrusion by the unauthorized third party and the entry path of the attack. To date, we have learned that an unauthorized third party leveraged malware deployed to a CircleCI engineer’s laptop in order to steal a valid, 2FA-backed SSO session. This machine was compromised on December 16, 2022. The malware was not detected by our antivirus software. Our investigation indicates that the malware was able to execute session cookie theft, enabling them to impersonate the targeted employee in a remote location and then escalate access to a subset of our production systems.

[Cloudflare](https://web.archive.org/web/20211029020126/https://blog.cloudflare.com/incident-report-on-memory-leak-caused-by-cloudflare-parser-bug/). A parser bug caused Cloudflare edge servers to return memory that contained private information such as HTTP cookies, authentication tokens, HTTP POST bodies, and other sensitive data.

[Cloudflare](https://web.archive.org/web/20211006055154/https://blog.cloudflare.com/details-of-the-cloudflare-outage-on-july-2-2019/). A CPU exhaustion was caused by a single WAF rule that contained a poorly written regular expression that ended up creating excessive backtracking. This rule was deployed quickly to production and a series of events lead to a global 27 minutes downtime of the Cloudflare services.

[CrowdStrike](https://www.crowdstrike.com/falcon-content-update-remediation-and-guidance-hub/). A Content update containing undetected errors was deployed due to a bug in the Content Validator in the deployment stage. This problematic content caused an out-of-bounds memory read, resulting in a Windows operating system crash (BSOD) on 8.5 million Windows machines. The update was reverted within 78 minutes, but the incident highlighted the need for improved validation and testing processes.

[Datadog](https://www.datadoghq.com/blog/2023-03-08-multiregion-infrastructure-connectivity-issue/). After an automatic upgrade, all network rules were removed and caused a 24h duration outage of all their Cilium protected Kubernetes clusters in all their regions and cloud providers.

[Discord](https://status.discordapp.com/incidents/dj3l6lw926kl). A flapping service lead to a thundering herd reconnecting to it once it came up. This lead to a cascading error where frontend services ran out of memory due to internal queues filling up.

[Discord](https://status.discordapp.com/incidents/qk9cdgnqnhcn). "At approximately 14:01, a Redis instance acting as the primary for a highly-available cluster used by Discord's API services was migrated automatically by Google’s Cloud Platform. This migration caused the node to incorrectly drop offline, forcing the cluster to rebalance and trigger known issues with the way Discord API instances handle Redis failover. After resolving this partial outage, unnoticed issues on other services caused a cascading failure through Discord’s real time system. These issues caused enough critical impact that Discord’s engineering team was forced to fully restart the service, reconnecting millions of clients over a period of 20 minutes."

[Dropbox](https://blogs.dropbox.com/tech/2014/01/outage-post-mortem/). This postmortem is pretty thin and I'm not sure what happened. It sounds like, maybe, a scheduled OS upgrade somehow caused some machines to get wiped out, which took out some databases.

[Duo](https://status.duo.com/incidents/4w07bmvnt359). Cascading failure due to a request queue overloading the existing, insufficient database capacity. Inadequate capacity planning and monitoring could be attributed as well.

[Epic Games](https://web.archive.org/web/20220430011642/https://www.epicgames.com/fortnite/en-US/news/postmortem-of-service-outage-at-3-4m-ccu). Extreme load (a new peak of 3.4 million concurrent users) resulted in a mix of partial and total service disruptions.

[European Space Agency](https://en.wikipedia.org/wiki/Cluster_%28spacecraft%29?oldid=217305667). An overflow occurred when converting a 16-bit number to a 64-bit numer in the Ariane 5 intertial guidance system, causing the rocket to crash. The actual overflow occurred in code that wasn't necessary for operation but was running anyway. According to [one account](https://web.archive.org/web/20120829114850/https://www.around.com/ariane.html), this caused a diagnostic error message to get printed out, and the diagnostic error message was somehow interpreted as actual valid data. According to [another account](https://en.wikipedia.org/wiki/Cluster_%28spacecraft%29?oldid=217305667), no trap handler was installed for the overflow.

[Elastic](https://www.elastic.co/blog/elastic-cloud-january-18-2019-incident-report). Elastic Cloud customers with deployments in the AWS eu-west-1 (Ireland) region experienced severely degraded access to their clusters for roughly 3 hours. During this same timeframe, there was an approximately 20 minute period during which all deployments in this region were completely unavailable.

[Elastic](https://www.elastic.co/blog/elastic-cloud-incident-report-feburary-4-2019). Elastic Cloud customers with deployments in the AWS us-east-1 region experienced degraded access to their clusters.

[ESLint](https://eslint.org/blog/2018/07/postmortem-for-malicious-package-publishes). On July 12th, 2018, an attacker compromised the npm account of an ESLint maintainer and published malicious packages to the npm registry.

[Etsy](https://blog.etsy.com/news/2012/demystifying-site-outages/). First, a deploy that was supposed to be a small bugfix deploy also caused live databases to get upgraded on running production machines. To make sure that this didn't cause any corruption, Etsy stopped serving traffic to run integrity checks. Second, an overflow in ids (signed 32-bit ints) caused some database operations to fail. Etsy didn't trust that this wouldn't result in data corruption and took down the site while the upgrade got pushed.

[Fastly](https://www.fastly.com/blog/summary-of-june-8-outage). Global outage due to an undiscovered software bug that surfaced on June 8 when it was triggered by a valid customer configuration change.

[Flowdock](https://web.archive.org/web/20220704223244/https://flowdock-resources.s3.amazonaws.com/legal/Flowdock-RCA-For-Incident-On-2020-04-21.pdf). Flowdock instant messaging was unavailable for approx 24 hrs between April 21-22 2020. The COVID-19 pandemic caused a sudden and drastic increase in working from home, which caused a higher usage of Flowdock, which caused high CPU usage, which caused the application database to hang. Some user data was permanently lost.

[Foursquare](https://web.archive.org/web/20230602082218/https://news.ycombinator.com/item?id=1769761). MongoDB fell over under load when it ran out of memory. The failure was catastrophic and not graceful due to a a query pattern that involved a read-load with low levels of locality (each user check-in caused a read of all check-ins for the user's history, and records were 300 bytes with no spatial locality, meaning that most of the data pulled in from each page was unnecessary). A lack of monitoring on the MongoDB instances caused the high load to go undetected until the load became catastrophic, causing 17 hours of downtime spanning two incidents in two days.

[Gentoo](https://wiki.gentoo.org/wiki/Github/2018-06-28). An entity gained access to the Gentoo GitHub organization, removed access to all developers and started adding commits in various repositories.

[GitHub](https://githubengineering.com/ddos-incident-report/). On February 28th 2018, GitHub experienced a DDoS attack, hitting the website with 1.35Tbps of traffic.

[Gitlab](https://docs.google.com/document/d/1ScqXAdb6BjhsDzCo3qdPYbt1uULzgZqPO8zHeHHarS0/preview?sle=true&hl=en&forcehl=1#heading=h.dfbilqgnc5sf). After the primary locked up and was restarted, it was brought back up with the wrong filesystem, causing a global outage. See also [HN discussion](https://web.archive.org/web/20220127094354/https://news.ycombinator.com/item?id=8003601).

[Gitlab](https://about.gitlab.com/2017/02/10/postmortem-of-database-outage-of-january-31/). Influx of requests overloaded the database, caused replication to lag, tired admin deleted the wrong directory, six hours of data lost. See also [earlier report](https://about.gitlab.com/2017/02/01/gitlab-dot-com-database-incident) and [HN discussion](https://news.ycombinator.com/item?id=13537052).

[Google](https://gist.github.com/jomo/2bae3821acb433d0446d). A mail system emailed people more than 20 times. This happened because mail was sent with a batch cron job that sent mail to everyone who was marked as waiting for mail. This was a non-atomic operation and the batch job didn't mark people as not waiting until all messages were sent.

[Google](https://status.cloud.google.com/incidents/X8SNkK2BPyCrc1sveeiu). Filestore enforces a global limit on API requests to limit impact in overload scenarios. The outage was triggered when an internal Google service managing a large number of GCP projects malfunctioned and overloaded the Filestore API with requests, causing global throttling of the Filestore API. This continued until the internal service was manually paused. As a result of this throttling, read-only API access was unavailable for all customers. This affected customers in all locations, due to a global quota that applies to Filestore. Console, gcloud and API access (List, GetOperation, etc.) calls all failed for a duration of 3 hours, 12 minutes. Mutate operations (CreateInstance, UpdateInstance, CreateBackup, etc.) still succeeded, but customers were unable to check on operation progress.

[Google](https://www.google.com/appsstatus/dashboard/incidents/k71P8nHp32hgcMSsC3mR). The Google Meet Livestream feature experienced disruptions that caused intermittent degraded quality of experience for a small subset of viewers, starting 25 October 2021 0400 PT and ending 26 October 2021 1000 PT. Quality was degraded for a total duration of 4 hours (3 hours on 25 October and 1 hour on 26 October). During this time, no more than 15% of livestream viewers experienced higher rebuffer rates and latency in livestream video playback. We sincerely apologize for the disruption that may have affected your business-critical events. We have identified the cause of the issue and have taken steps to improve our service.

[Google](https://status.cloud.google.com/incidents/mREMLwZFe3FuLLn3zfTw). On 13 October 2022 23:30 US/Pacific, there was an unexpected increase of incoming and logging traffic combined with a bug in Google’s internal streaming RPC library that triggered a deadlock and caused the Write API Streaming frontend to be overloaded. And BigQuery Storage WriteAPI observed elevated error rates in the US Multi-Region for a period of 5 hours.

[GPS/GLONASS](https://www.gps.gov/governance/advisory/meetings/2014-06/beutler1.pdf). A bad update that caused incorrect orbital mechanics calculations caused GPS satellites that use GLONASS to broadcast incorrect positions for 10 hours. The bug was noticed and rolled back almost immediately due to (?) this didn't fix the issue.

[Healthcare.gov](https://web.archive.org/web/20201108122248/https://www.bloomberg.com/opinion/articles/2015-09-16/how-healthcare-gov-went-so-so-wrong). A large organizational failure to build a website for United States healthcare.

[Heroku](https://status.heroku.com/incidents/642?postmortem). Having a system that requires scheduled manual updates resulted in an error which caused US customers to be unable to scale, stop or restart dynos, or route HTTP traffic, and also prevented all customers from being able to deploy.

[Heroku](https://engineering.heroku.com/blogs/2017-02-15-filesystem-corruption-on-heroku-dynos/). An upgrade silently disabled a check that was meant to prevent filesystem corruption in running containers. A subsequent deploy caused filesystem corruption in running containers.

[Heroku](https://status.heroku.com/incidents/1042). An upstream `apt` update broke pinned packages which lead to customers experiencing write permission failures to `/dev`.

[Heroku](https://blog.heroku.com/april-2022-incident-review). Private tokens were leaked, and allowed attackers to retrieve data, both in internal databases, in private repositories and from customers accounts.

[Heroku](https://status.heroku.com/incidents/2451). A change to the core application that manages the underlying infrastructure for the Common Runtime included a dependency upgrade that caused a timing lock issue that greatly reduced the throughput of our task workers. This dependency change, coupled with a failure to appropriately scale up due to increased workload scheduling, caused the application's work queue to build up. Contributing to the issue, the team was not alerted immediately that new router instances were not being initialized correctly on startup largely because of incorrectly configured alerts. These router instances were serving live traffic already but were shown to be in the wrong boot state, and they were deleted via our normal processes due to failing readiness checks. The deletion caused a degradation of the associated runtime cluster while the autoscaling group was creating new instances. This reduced pool of router instances caused requests to fail as more requests were coming in faster than the limited number of routers could handle. This is when customers started noticing issues with the service.

[Homebrew](https://web.archive.org/web/20210813020247/https://brew.sh/2018/08/05/security-incident-disclosure/). A GitHub personal access token with recently elevated scopes was leaked from Homebrew’s Jenkins that allowed access to `git push` on several Homebrew repositories.

[Honeycomb](https://www.honeycomb.io/blog/incident-resolution-september-retrospective/). A tale of multiple incidents, happening mostly due to fast growth.

[Honeycomb](https://www.honeycomb.io/blog/incident-review-designed-failing/). Another story of multiple incidents that ended up impacting [query performance](https://status.honeycomb.io/incidents/fzw6hqjx5t4f) and [alerting via triggers and SLOs](https://status.honeycomb.io/incidents/jwhrxcs5zr06). These incidents were notable because of how challenging their investigation turned out to be.

[Honeycomb](https://www.honeycomb.io/blog/incident-review-shepherd-cache-delays/). On September 8th, 2022, our ingest system went down repeatedly and caused interruptions for over eight hours. We will first cover the background behind the incident with a high-level view of the relevant architecture, how we tried to investigate and fix the system, and finally, we’ll go over some meaningful elements that surfaced from our incident review process.

[Honeycomb](https://www.honeycomb.io/blog/incident-review-what-comes-up-must-first-go-down/). On July 25th, 2023, we experienced a total Honeycomb outage. It impacted all user-facing components from 1:40 p.m. UTC to 2:48 p.m. UTC, during which no data could be processed or accessed. The full details of incident triage process is covered in [here](https://www.honeycomb.io/wp-content/uploads/2023/08/Incident-Review-What-Comes-Up-Must-First-Go-Down.pdf).

[incident.io](https://incident.io/blog/intermittent-downtime). A bad event (poison pill) in the async workers queue triggered unhandled panics that repeatedly crashed the app. This combined poorly with Heroku infrastructure, making it difficult to find the source of the problem. Applied mitigations that are generally interesting to people running web services, such as catching corner cases of Go panic recovery and splitting work by type/class to improve reliability.

[Indian Electricity Grid](https://web.archive.org/web/20220124104632/https://cercind.gov.in/2012/orders/Final_Report_Grid_Disturbance.pdf). One night in July 2012, a skewed electricity supply-demand profile developed when the northern grid drew a tremendous amount of power from the western and eastern grids. Following a series of circuit breakers tripping by virtue of under-frequency protection, the entire NEW (northern-eastern-western) grid collapsed due to the absence of islanding mechanisms. While the grid was reactivated after over 8 hours, similar conditions in the following day caused the grid to fail again. However, the restoration effort concluded almost 24 hours after the occurrence of the latter incident.

[Instapaper](https://web.archive.org/web/20211124170124/https://medium.com/making-instapaper/instapaper-outage-cause-recovery-3c32a7e9cc5f). Also [this](https://web.archive.org/web/20240911020547/https://blog.instapaper.com/post/157027537441). Limits were hit for a hosted database. It took many hours to migrate over to a new database.

[Intel](https://web.archive.org/web/20241105190743/http://42gems.com/blog/?p=735). A scripting bug caused the generation of the divider logic in the Pentium to very occasionally produce incorrect results. The bug wasn't caught in testing because of an incorrect assumption in a proof of correctness. (See [the Wikipedia article on 1994 FDIV bug](https://en.wikipedia.org/wiki/Pentium_FDIV_bug) for more information.)

[Joyent](https://web.archive.org/web/20220528044329/https://www.joyent.com/blog/manta-postmortem-7-27-2015). Operations on Manta were blocked because a lock couldn't be obtained on their PostgreSQL metadata servers. This was due to a combination of PostgreSQL's transaction wraparound maintenance taking a lock on something, and a Joyent query that unnecessarily tried to take a global lock.

[Joyent](https://web.archive.org/web/20220406095752/https://www.joyent.com/blog/postmortem-for-outage-of-us-east-1-may-27-2014). An operator used a tool with lax input validation to reboot a small number of servers undergoing maintenance but forgot to type `-n` and instead rebooted all servers in the datacenter. This caused an outage that lasted 2.5 hours, rebooted all customer instances, put tremendous load on DHCP/TFTP PXE boot systems, and left API systems requiring manual intervention. See also [Bryan Cantrill's talk](https://www.youtube.com/watch?v=30jNsCVLpAE).

[Kickstarter](https://web.archive.org/web/20170728131458/https://kickstarter.engineering/the-day-the-replication-died-e543ba45f262). Primary DB became inconsistent with all replicas, which wasn't detected until a query failed. This was caused by a MySQL bug which sometimes caused `order by` to be ignored.

[Kings College London](https://regmedia.co.uk/2017/02/23/kcl_external_review.pdf). 3PAR suffered catastrophic outage which highlighted a failure in internal process.

[Launchdarkly](https://status.launchdarkly.com/incidents/yltrp45vtxm2). Rule attribute selector causing flag targeting web interface to crash.

[Mailgun](https://status.mailgun.com/incidents/p9nxxql8g9rh). Secondary MongoDB servers became overloaded and while troubleshooting accidentally pushed a change that sent all secondary traffic to the primary MongoDB server, overloading it as well and exacerbating the problem.

[Mandrill](https://mailchimp.com/what-we-learned-from-the-recent-mandrill-outage/). Transaction ID wraparound in Postgres caused a partial outage lasting a day and a half.

[Medium](https://web.archive.org/web/20160426163728/https://medium.com/medium-eng/the-curious-case-of-disappearing-polish-s-fa398313d4df). Polish users were unable to use their "Ś" key on Medium.

[Metrist](https://web.archive.org/web/20230927050430/https://metrist.io/blog/how-we-found-azures-unannounced-breaking-change/). Azure published a breaking change that affected downstream systems like Metrist's service without warning them, the post covers how to identify the issue and how to recover from it.

[NASA](https://www.doneyles.com/LM/Tales.html). A design flaw in the Apollo 11 rendezvous radar produced excess CPU load, causing the spacecraft computer to restart during lunar landing.

[NASA](https://en.wikipedia.org/wiki/Mars_Climate_Orbiter). Use of different units of measurement (metric vs. English) caused Mars Climate Orbiter to fail. There were also organizational and procedural failures[[ref](https://space.stackexchange.com/a/20241)] and defects in the navigation software[[ref](https://spectrum.ieee.org/aerospace/robotic-exploration/why-the-mars-probe-went-off-course)].

[NASA](https://web.archive.org/web/20161230103247/https://research.microsoft.com/en-us/um/people/mbj/Mars_Pathfinder/Authoritative_Account.html). NASA's Mars Pathfinder spacecraft experienced system resets a few days after landing on Mars (1997).  Debugging features were remotely enabled until the cause was found: a [priority inversion](https://en.wikipedia.org/wiki/Priority_inversion) problem in the VxWorks operating system.  The OS software was remotely patched (all the way to Mars) to fix the problem by adding priority inheritance to the task scheduler.

[Netflix](https://netflixtechblog.com/post-mortem-of-october-22-2012-aws-degradation-efcee3ab40d5). An EBS outage in one availability zone was mitigated by migrating to other availability zones.

[North American Electric Power System](https://www3.epa.gov/region1/npdes/merrimackstation/pdfs/ar/AR-1165.pdf).  A power outage in Ohio around 1600h EDT cascaded up through a web of systemic vulnerabilities and process failures and resulted in an outage in the power grid affecting ~50,000,000 people for ~4 days in some areas, and caused rolling blackouts in Ontario for about a week thereafter.

[Okta](https://www.okta.com/blog/2022/03/oktas-investigation-of-the-january-2022-compromise/). A hackers group got access to a third-party support engineer's laptop.

[OpenAI](https://web.archive.org/web/20240426015133/https://openai.com/blog/march-20-chatgpt-outage). Queues for requests and responses in a Redis cache became corrupted and out of sequence, leading to some requests revealing other people's user data to some users, including app activity data and some billing info.

[Pagerduty](https://web.archive.org/web/20211019062735/https://www.pagerduty.com/blog/outage-post-mortem-april-13-2013/). In April 2013, [Pagerduty](https://web.archive.org/web/20220906003007/https://www.pagerduty.com/), a cloud service proving application uptime monitoring and real-time notifications, suffered an outage when two of its three independent cloud deployments in different data centers began experiencing connectivity issues and high network latency. It was found later that the two independent deployments shared a common peering point which was experiencing network instability.  While the third deployment was still operational, Pagerduty's applications failed to establish quorum due to to high network latency and hence failed in their ability to send notifications.

[PagerDuty](https://status.pagerduty.com/incidents/70m30bh7qfmx). A third party service for sending SMS and making voice calls experienced an outage due to AWS having issues in a region.

[Parity](https://paritytech.io/the-multi-sig-hack-a-postmortem/). $30 million of cryptocurrency value was diverted (stolen) with another $150 million diverted to a safe place (rescued), after a 4000-line software change containing a security bug was mistakenly labeled as a UI change, inadequately reviewed, deployed, and used by various unsuspecting third parties. See also [this analysis](https://web.archive.org/web/20221226010429/https://hackingdistributed.com/2017/07/22/deep-dive-parity-bug/).

[Platform.sh](https://web.archive.org/web/20201202234639/https://medium.com/@florian_7764/technical-post-mortem-of-the-august-incident-82ab4c3d6547). Outage during a scheduled maintenance window because there were too much data for Zookeeper to boot.

[Reddit](https://web.archive.org/web/20221029203405/https://www.reddit.com/r/announcements/comments/4y0m56/why_reddit_was_down_on_aug_11/). Experienced an outage for 1.5 hours, followed by another 1.5 hours of degraded performance on Thursday August 11 2016. This was due to an error during a migration of a critical backend system.

[Reddit](https://web.archive.org/web/20230727225235/https://www.reddit.com/r/RedditEng/comments/11xx5o0/you_broke_reddit_the_piday_outage/). Outage for over 5 hours when a critical Kubernetes cluster upgrade failed. The failure was caused by node metadata that changed between versions which brought down workload networking.

[Roblox](https://blog.roblox.com/2022/01/roblox-return-to-service-10-28-10-31-2021/). Roblox end Oct 2021 73 hours outage. Issues with Consul streaming and BoltDB.

[Salesforce](https://help.salesforce.com/apex/HTViewSolution?urlname=Root-Cause-Message-for-Disruption-of-Service-on-NA14-May-2016&language=en_US). Initial disruption due to power failure in one datacenter led to cascading failures with a database cluster and file discrepancies resulting in cross data center failover issues.

[Salesforce](https://help.salesforce.com/s/articleView?id=000396429&type=1). On September 20, 2023, a service disruption affected a subset of customers across multiple services beginning at 14:48 Coordinated Universal Time (UTC). As a result, some customers were unable to login and access their services. A policy change executed as a part of our standard security controls review and update cycle to be the trigger of this incident. This change inadvertently blocked access to resources beyond its intended scope.

[Sentry](https://blog.sentry.io/2015/07/23/transaction-id-wraparound-in-postgres). Transaction ID Wraparound in Postgres caused Sentry to go down for most of a working day.

[Shapeshift](http://web.archive.org/web/20160610080136/https://www.scribd.com/doc/309574927/ShapeShift-Post-Mortem-Public). Poor security practices enabled an employee to steal $200,000 in cryptocurrency in 3 separate hacks over a 1 month period. The company's CEO expanded upon the story in a [blog post](https://web.archive.org/web/20190811214903/http://moneyandstate.com:80/looting-of-the-fox/).

[Skyliner](https://blog.skyliner.io/post-mortem-outages-on-1-19-17-and-1-23-17-3f65cc6f693e). A memory leak in a third party library lead to Skyliner being unavailable on two occasions.

[Slack](https://web.archive.org/web/20181208123409/https://slackhq.com/this-was-not-normal-really). A combination of factor results in a large number of Slack's users being disconnected to the server. The subsequent massive disconnection-reconnection process exceeded the database capacity and caused cascading connection failures, leading to 5% of Slack's users not being able to connect to the server for up to 2 hours.

[Slack](https://slack.engineering/slacks-outage-on-january-4th-2021/). Network saturation in AWS's traffic gateways caused packet loss. An attempt to scale up caused more issues.

[Slack](https://slack.engineering/slacks-incident-on-2-22-22/). Cache nodes removal caused the high workload on the vitness cluster, which in turn cased the service outage.

[Spotify](https://labs.spotify.com/2013/06/04/incident-management-at-spotify/). Lack of exponential backoff in a microservice caused a cascading failure, leading to notable service degradation.

[Square](https://web.archive.org/web/20210818034431/https://medium.com/square-corner-blog/incident-summary-2017-03-16-2f65be39297). A cascading error from an adjacent service lead to merchant authentication service being overloaded. This impacted merchants for ~2 hours.

[Stackdriver](https://www.stackdriver.com/post-mortem-october-23-stackdriver-outage/). In October 2013, [Stackdriver](https://www.stackdriver.com/), experienced an outage, when its Cassandra cluster crashed. Data published by various services into a message bus was being injested into the Cassandra cluster. When the cluster failed, the failure percolated to various producers, that ended up blocking on queue insert operations, eventually leading to the failure of the entire application.

[Stack Exchange](http://web.archive.org/web/20150404235419/https://stackstatus.net/post/115305251014/outage-postmortem-march-31-2015). Enabling StackEgg for all users resulted in heavy load on load balancers and consequently, a DDoS.

[Stack Exchange](http://web.archive.org/web/20160720200842/https://stackstatus.net/post/147710624694/outage-postmortem-july-20-2016). Backtracking implementation in the underlying regex engine turned out to be very expensive for a particular post leading to health-check failures and eventual outage.

[Stack Exchange](https://meta.stackoverflow.com/q/340960/2422776). Porting old Careers 2.0 code to the new Developer Story caused a leak of users' information.

[Stack Exchange](http://web.archive.org/web/20170130231315/https://stackstatus.net/post/156407746074/outage-postmortem-january-24-2017). The primary SQL-Server triggered a bugcheck on the SQL Server process, causing the Stack Exchange sites to go into read only mode, and eventually a complete outage.

[Strava](https://engineering.strava.com/the-upload-outage-of-july-29-2014/). Hit the signed integer limit on a primary key, causing uploads to fail.

[Stripe](https://support.stripe.com/questions/outage-postmortem-2015-10-08-utc). Manual operations are regularly executed on production databases. A manual operation was done incorrectly (missing dependency), causing the Stripe API to go down for 90 minutes.

[Sweden](https://www.pri.org/stories/2012-02-23/new-clues-emerge-centuries-old-swedish-shipwreck). Use of different rulers by builders caused the _Vasa_ to be more heavily built on its port side and the ship's designer, not having built a ship with two gun decks before, overbuilt the upper decks, leading to a design that was top heavy. Twenty minutes into its maiden voyage in 1628, the ship heeled to port and sank.

[Tarsnap](https://mail.tarsnap.com/tarsnap-announce/msg00035.html). A batch job which scans for unused blocks in Amazon S3 and marks them to be freed encountered a condition where all retries for freeing certain blocks would fail. The batch job logs its actions to local disk and this log grew without bound. When the filesystem filled, this caused other filesystem writes to fail, and the Tarsnap service stopped. Manually removing the log file restored service.

[Telstra](https://web.archive.org/web/20170202055452/https://www.businessinsider.com.au/a-fire-in-a-telstra-exchange-is-causing-flight-delays-and-network-outages-2017-2). A fire in a datacenter caused SMS text messages to be sent to random destinations. Corrupt messages were also experienced by customers.

[Therac-25](http://sunnyday.mit.edu/papers/therac.pdf). The Therac-25 was a radiation therapy machine involved in at least six accidents between 1985 and 1987 in which patients were given massive overdoses of radiation. Because of concurrent programming errors, it sometimes gave its patients radiation doses that were thousands of times greater than normal, resulting in death or serious injury.

[trivago](https://tech.trivago.com/2021/10/05/postmortem-removing-all-users-from-github.com/trivago/). Due to a human error, all engineers lost access to the central source code management platform (GitHub organization). An Azure Active Directory Security group controls the access to the GitHub organization. This group was removed during the execution of a manual and repetitive task.

[Twilio](https://www.twilio.com/blog/2013/07/billing-incident-post-mortem-breakdown-analysis-and-root-cause.html). In 2013, a temporary network partition in the redis cluster used for billing operations, caused a massive resynchronization from slaves. The overloaded master crashed and when it was restarted, it started up in read-only mode. The auto-recharge component in This resulted in failed transactions from Twilio's auto-recharge service, which unfortunately billed the customers before updating their balance internally. So the auto-recharge system continued to retry the transaction again and again, resulting in multiple charges to customer's credit cards.

[Twilio](https://status.twilio.com/incidents/wdrlk4qps0z1). Twilio's incident of having high filtering on SMS towards AT&T Network In United States.

[Valve](https://github.com/valvesoftware/steam-for-linux/issues/3671). Steam's desktop client deleted all local files and directories. The thing I find most interesting about this is that, after this blew up on social media, there were widespread reports that this was reported to Valve months earlier. But Valve doesn't triage most bugs, resulting in an extremely long time-to-mitigate, despite having multiple bug reports on this issue.

[Yeller](https://web.archive.org/web/20201018145502/http://yellerapp.com/posts/2014-08-04-postmortem1.html). A network partition in a cluster caused some messages to get delayed, up to 6-7 hours. For reasons that aren't clear, a rolling restart of the cluster healed the partition. There's some suspicious that it was due to cached routes, but there wasn't enough logging information to tell for sure.

[Zerodha](https://zerodha.com/marketintel/bulletin/229363/post-mortem-of-technical-issue-august-29-2019). The Order Management System (OMS) provided to Zerodha, a stock broker, collapsed when an order for 1M units of a penny stock was divided into more than 0.1M individual trades against the typical few hundreds, triggering a collapse of the OMS, which was not encountered prior by its provider - Refinitiv (formerly Thomson Reuters), a subsidiary of the London Stock Exchange.

[Zerodha](https://zerodha.com/marketintel/bulletin/105569/postmortem-trading-and-hanging-orders-on-12th-april-2018). A failure of the primary leased line to a CTCL between a stock broker and a stock exchange led to the activation of a backup leased line that was operating sporadically over the following hour, affecting bracket and cover orders. Subsequently, the process of placing and validating orders had been modified to incorporate the unreliability of the CTCL's leased lines, but the reliability of the primary and the backup leased lines was not fundamentally improved by the providers.

*Unfortunately, most of the interesting post-mortems I know about are locked inside confidential pages at Google and Microsoft. Please add more links if you know of any interesting public post mortems!  is a pretty good resource; other links to collections of post mortems are also appreciated.*

## Other lists of postmortems

[AWS Post-Event Summaries](https://aws.amazon.com/premiumsupport/technology/pes/)

[Availability Digest website](https://web.archive.org/web/20190914025003/http://www.availabilitydigest.com:80/articles.htm).

[Postmortems community](https://web.archive.org/web/20230329091806/https://postmortems.info/) (with imported archive from the now-dead G+ community).

[John Daily's list of postmortems (in json)](https://github.com/macintux/Service-postmortems).

[Jeff Hammerbacher's list of postmortems](https://www.quora.com/Jeff-Hammerbacher/Post-mortems).

[NASA lessons learned database](https://llis.nasa.gov/).

[Tim Freeman's list of postmortems](https://pinboard.in/u:peakscale/t:postmortem/)

[Wikimedia's postmortems](https://wikitech.wikimedia.org/wiki/Incident_documentation).

[Autopsy.io's list of Startup failures](https://web.archive.org/web/20190101075846/http://autopsy.io/).

[SRE Weekly](https://sreweekly.com) usually has an **Outages** section at the end.

[Lorin Hochstein's list of major incidents](https://github.com/lorin/major-incidents).

[Awesome Tech Postmortems](https://github.com/snakescott/awesome-tech-postmortems).

[Nat Welch's parsed postmortems](https://github.com/icco/postmortems) is an attempt to build a database out of this markdown file.

[Postmortem Templates](https://github.com/dastergon/postmortem-templates) is a collection of postmortem templates from various sources.

## Analysis

[How Complex Systems Fail](https://stuff.mit.edu/afs/athena/course/2/2.75/resources/random/How%20Complex%20Systems%20Fail.pdf)

[John Allspaw on Resilience Engineering](https://www.kitchensoap.com/2011/04/07/resilience-engineering-part-i/)

## Contributors

* Aaron Wigley
* Ahmet Alp Balkan
* Allon Murienik
* Amber Yust
* Anirudh Ramesh
* Anthony Elizondo
* Anuj Pahuja
* Benjamin Gilbert
* Ben Zanin
* Brad Baris
* Brendan McLoughlin
* Brent Eritou
* Brian Scanlan
* Brock Boland
* Chris Higgs
* Chris Sinjakli
* Connor Shea
* Damien Mathieu
* Dan Luu
* Dan Nguyen
* David Pate
* Dov Murik
* Ed Spittles
* Florent Genette
* Franck Arnulfo
* gnomon
* Grey Baker
* Isaac Rogers
* Jacob Kaplan-Moss
* James Graham
* Jameson Lopp
* Jason Dusek
* Jens Rantil
* John Daily
* jomo
* Julia Hansbrough
* Julian Szulc
* Justin Montgomery
* KS Chan
* Kevin Brown
* KlavierCat
* Kunal Mehta
* Luan Cestari
* Marcin Wasiluk
* Mark Dennehy
* Massimiliano Arione
* Matt Day
* Michael Robinson
* Michał Kosmulski
* Mike Doherty
* Mohit Agarwal
* Nat Welch
* Nate Parsons
* Nick Sweeting
* Nicola Corti
* Owen Jacobson
* Peter Demin
* Raul Ochoa
* Ruairi Carroll
* Rui Chen
* Samuel Hunter
* Sean Escriva
* Shriram Rajagopalan
* Siddharth Kannan
* Tamir Dresher
* Tim Freeman
* Tom Crayford
* Valdeci Gomes
* Vaibhav Bhembre
* Veit Heller
* Vincent Ambo
