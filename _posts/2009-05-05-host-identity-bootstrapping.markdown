---

title: Host identity bootstrapping
abstract: Automated provisioning of hosts on a network with reasonable levels of security is described in this application. A certificate management service (CMS) on a host, one or more trusted agents, and a public key infrastructure are utilized in a secure framework to establish host identity. Once host identity is established, signed encryption certificates may be exchanged and secure communication may take place.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09432356&OS=09432356&RS=09432356
owner: Amazon Technologies, Inc.
number: 09432356
owner_city: Seattle
owner_country: US
publication_date: 20090505
---
Provisioning is the installation and configuration of an end entity on a network. This end entity or host may be a router network attached storage physical server virtual server etc. Traditionally provisioning involves human interaction to establish the identity of the device. This establishment of host identity allows other security processes to reliably know who the host is in order to ensure that only those hosts that are authorized to run a particular service do so.

Various schemes have been put forth to streamline and automate provisioning. However these provisioning techniques rely upon a human actor to complete the provisioning process by participating in the establishment of the host identity. Virtual servers provide multiple separate server instances executing on common physical host with each instance requiring separate provisioning. With the increasing population of servers both physical and virtual the problem becomes more challenging.

In large data center environments this requirement for human interaction can lead to delays in provisioning as well as increased operational costs. Thus there is a need for reasonably secure automated identification of hosts prior to their being turned over to production in order to permit fully automated provisioning of hosts.

As described above provisioning of hosts including servers in a data center has traditionally involved human interaction. Currently available solutions still ground the root of trust of a host s identity in a human that authorized the provisioning of a newly installed host and thus are not completely automated. Other available solutions rely on placement within a network to establish identity a reliance which breaks down in large data center environments.

This disclosure describes techniques for automating the provisioning process. Using techniques described herein host identity may be established to a network without human intervention even before an operating system OS is fully instantiated on the host being provisioned. Once the host OS boots a certificate management service loads and automatically retrieves one or more encryption certificates certificates from a certificate authority CA . In one example this certificate retrieval may utilize hypertext transport protocol secure HTTPS . The certificates allow future secure communications between the host and the network. Certificates may also be renewed for a provisioned host without human intervention. Exceptional circumstances such as a change in the hardware may cause a change in the hardware identification HWID of the requesting host. This would make it a new host and require a new certificate.

The value of encryption certificates in the context of this application is not in the mere possession by a host of the encryption certificate. Possession only proves that a host has a certificate issued by an appropriate certificate authority. Rather the value of the certificate is in the permissions granted to the identity authenticated by possession of the certificate such as the host hostclass mapping. So while a rogue host may obtain a certificate only legitimate hosts can take actions of value such as obtaining the software necessary to be a member of a hostclass. A host class is a grouping of hosts and may be maintained by a trusted centralized authority. Thus the issuance of a certificate is not necessarily a sensitive operation but rather provisioning a host into a hostclass or otherwise trusting a host that has proven its identity is a sensitive operation. The establishment of identity during the provisioning process is discussed in more detail next.

Security services used to provide secure web services include authentication access control and auditing. Auditing requires among other things authentication to establish the actor attempting access and service access controls to determine what the actor did. This authentication may rely on some form of key management . Service access control in turn depends upon binding an authenticated identity with a resource. Service to service authentication further requires an authenticated identity. The authenticated service identity depends on there being a service identity in the first place.

However the service identity is only as trustworthy as the manner in which that service was imbued with its identity. If a service is provisioned with its proof of identity after someone who could be untrusted has touched it the identity may be untrustworthy. Thus some sort of host identity framework is called for.

Within host identity framework a network provides communication between devices which are attached to it. Network may comprise an Ethernet Wi Fi Token Ring Fibre Channel or other network including hardware and or software configured to permit communication between devices. For illustration only and not by way of limitation the network in this application is described in the context of an Ethernet network using the internet protocol suite Transmission Control Protocol TCP and Internet Protocol IP .

Trusted agent s attached to network may include several entities. These trusted agent s may include a build out server BOS which provides build out information to a host and updates a host management database HMDB to reflect the host status and hardware identification HWID of the new host. HMDB provides storage and retrieval of host information such as host status and HWID values. Each HWID is associated with a particular instantiation of an operating system and not necessarily the specific underlying hardware in which the OS is running. For example each instantiation of an operating system on each virtual server on a common physical server would have a different HWID.

A permissions database PDB provides a permissions service which maintains a database of network resources accessible to specific encryption certificates.

A trusted issuer server TIS provides a certificate signing request CSR request processing service and responds to valid requests for CSRs from hosts with a CSR.

An infrastructure coordination server ICS provides a management interface and facilitates communication between the hosts public key infrastructure and trusted agent s . The ICS also provides a level of abstraction allowing interaction and management between different security domains. For example an ICS would allow a host in a production security domain to interact with servers in an experimental security domain.

A public key infrastructure PKI is also included in the host identity framework . PKI may include a Certificate Authority Server CAS and Registration Authority Server RAS . CAS signs encryption certificates while RAS may act as a proxy for the CAS . In other implementations portions of PKI may be operated by a same or different entity as an end entity and or trusted agents .

End entities are also included in the host identity framework . These end entities may include servers routers storage devices virtualized instances or other unique computing resource that needs an identification certificate. Host may be such an end entity that is or needs to be authenticated to the network .

While shown as discrete devices the servers and databases shown in may be consolidated or distributed across several physical or virtual devices. For example in one implementation TIS and host may be deployed as virtualized instances across a shared physical host. In such an implementation a high degree of trust may be assumed for communication via a trusted control channel between these virtualized servers on shared computing hardware. This control channel may include a virtual networking connection between the virtualized servers shared memory such as a common disk or memory location and so forth. Thus use of virtualized servers on shared computing hardware may result in increased security resulting from a greater level of trust for data exchanged between server instances via the control channel.

A certificate management service module CMSM is configured to request CSR s from TIS or self generate CSRs send those CSRs to CAS and receive store and control access to encryption certificates on the host . CMSM may also provide application programming interfaces APIs to sign encryption certificates for other services on host .

A local certificate storage module LCSM may handle the storage and retrieval of encryption certificates for the CMSM . The LCSM may be stored securely in memory on the host and in some implementations is accessible only by the service account used for the CMSM .

Stored within memory is hypervisor . A hypervisor may also be referred to as a virtual machine monitor VMM and provides an environment where multiple instances of operating systems may run concurrently on the same physical hardware.

Also within memory are virtualized server instances or virts . These virts may include host CAS ICS as shown as well as other servers and components from the trusted agent s PKI and or end entities . For example in another implementation virts may include host RAS and BOS .

Control channel is shown between hypervisor and the host CAS and ICS virts . This control channel remains within the memory of the same physical host and thus may be considered highly trusted and secure. A network interface may also be coupled to the processor and to the network .

At block BOS receives an inventory from host after the host initially powers up and executes assimilation module . At block BOS also updates HMDB to set a host status indicating that assembly is in progress to set a hardware identifier HWID and to set a provisioning expiration date. At block BOS sends the host a boot workflow.

At block host processes the boot workflow and initiates the OSIM which in turn requests an OS image from the OSIS . At block OSIS retrieves the HWID. At block OSIS builds an OS image which incorporates this HWID and provides the OS image to host . At block host begins the installation of the OS image. When the installation has progressed sufficiently to allow local storage at block host may access its local HWID and store the HWID .

For additional security the OSIM may close all network interfaces on the host during the deployment process at block except for a control channel. This control channel permits communication with the BOS . Where the OSIM and host are virts on the same physical host the control channel between those virts may be considered highly secure.

At block host starts the CMSM upon boot of the OS. At block host determines at the CMSM when a self generated CSR is permitted. Depending upon security policies for the network CSRs may either be self generated at host or requested from the TIS . In a high security environment using virtualized server implementations the TIS may be a virtualized server instance controlling the physical hardware the virtualized host is executing on. Thus the communications between TIS and host which takes advantage of a control channel between virts may be considered highly secure.

When such as in high security environments self generated CSRs are not allowed at block at block the TIS may receive a request for CSR from host . In one implementation block may be processed by CSRPM . In one implementation CSRPM may issue an alert if the HWID has previously been issued a CSR. As described above with respect to where the TIS and host are separate virtualized instances executing on shared computing hardware a high level of trust may be placed in data exchanged via a control channel between virtualized instances.

At block TIS may determine a hostclass of the host and provides the CSR to host . This hostclass assigns the host to a class permitted access to network resources.

When self generated CSRs are allowed at block at block host may self generate a CSR. In one implementation block may be processed by CMSM and KGM .

At block host sends the CSR to CAS . As described above with respect to where the host and CAS are virtualized instances executing on shared computing hardware such as a single physical host a high level of trust may be placed in data exchanged via a control channel between virtualized instances.

Block on CAS verifies the CSR as described in more detail below in . In one implementation block may be processed by VSM .

For additional security on CAS CAM may require additional verification of host identity and status. When CAM requires this additional verification at block at block CAM verifies identity and host status. This additional verification is described in more detail below in .

At block CAS retrieves a signed encryption certificate from the CAM with the CSR. At block CAS updates the HMDB to indicate an encryption certificate has been issued to the HWID assigned to host and sets a provisioning expiration date. At block CAS provides the encryption certificate to host . In one implementation at block CAS may use a secure channel to further safeguard the encryption certificate. In other implementations block may actively send information to host or wait for the host to poll the CAS .

At block VSM determines if a CSR is unsigned. When VSM determines that the host status in the HMDB indicates assembly is in progress for the HWID referenced in the unsigned CSR at block at block VSM determines if the provisioning expiration date in HMDB for this host is less than a threshold value. For example the threshold may be set for eight hours thus a CSR which is received within that eight hour window would be allowed. At block VSM thus determines if a host requesting a CSR is in fact one being provisioned or if the host is a rogue. The HMDB or other entity may update host status from indicating assembly is in progress to a dead or otherwise invalid status after a pre determined length of time. This would prevent a host which has a stalled installation process from being exploited by a rogue host.

When VSM at block determines that the provisioning expiration date is less than a predetermined threshold block permits issuance of an encryption certificate.

When VSM at block determines a CSR is signed if VSM at block determines a CSR is signed by a certificate with the same HWID as that being requested at block VSM permits issuance of an encryption certificate.

When at block VSM determines a CSR is signed by a certificate with a different HWID as that being requested at block VSM determines if the CSR is signed by an entity authorized to issue certificates. When VSM at block determines the CSR is signed by an entity authorized to issue certificates at block VSM permits issuance of an encryption certificate.

Otherwise if none of the foregoing conditions is met permission to issue a certificate is denied by VSM at block .

At block CAM verifies that the host status in the HMDB indicates a status of assembly in progress. At block CAM resolves the network address such as an IP address of the host at a name server such as a domain name server and sends a confirmation request to this resolved network address. Instead of trusting the network address provided in the CSR request the name is resolved in the name server to a network address listed for the host name indicated in the CSR request and the confirmation is sent to the resolved network address. This provides an additional layer of verification. This additional layer of verification increases the level of complexity required for an attack or spoof.

Upon receipt of the confirmation request of block host may respond by resending the CSR to the CAM . At block CAM verifies that the original CSR and the re sent CSR match. When CAM at block indicates a match at block CAM indicates that the host identity and status has been verified and the certificate process may proceed. When CAM at block indicates no match at block CAM denies the CSR thus denying issuance of an encryption certificate.

At an inventory including HWID is sent from AM on host to BOS . At BOS sets host status in the HMDB and sets the certificate expiration date to null. At BOS provides a boot workflow to AM on host . At AM passes the boot workflow to OSIM . At OSIM requests a boot image from OSIS . At OSIS retrieves the HWID from HMDB and builds an OS image incorporating the HWID. At OSIS provides the boot image with the HWID to OSIM . At OSIM stores the HWID in HWID file locally on host .

At OSIM completes the OS boot and passes configuration data to CMSM . At HWID may be provided to CSM . At KGM may provide public private key pairs to CMSM .

In one implementation to realize greater security and utilize the trusted channel between virts when self generation of a CSR is not permitted by the configuration provided to the host as part of the boot workflow at CMSM requests a CSR from TIS . At in response to TIS provides a CSR to CMSM . As described above with respect to where the TIS and host are separate virtualized instances executing on shared computing hardware a high level of trust may be placed on the CSR data exchanged via a control channel between virtualized instances.

At CMSM provides the CSR to VSM . At VSM retrieves host information as described above such as HWID host status and certificate expiration date. At HPPSM provides information for verifying that BOS has authority to issue a CSR for the requested hostclass. At the verified CSR is passed to CAM .

When confirmation at the CAM is desired as discussed with reference to above at a confirmation of CSR is initiated to CMSM . At CMSM provides the confirming CSR to CAM which issues an encryption certificate. At VSM updates the HMDB to reflect that an encryption certificate has been issued and to include the expiration date of the encryption certificate host status etc. At the issued encryption certificate is provided to CMSM . As described above with respect to where the CAS and host are virtualized on shared computing hardware data exchanged via a control channel between virtualized instances may be accorded a high level of trust. At the CMSM stores the encryption certificate in the LCSM for later use.

An alternative to the automated provisioning described above which includes a TIS is possible. In this alternative ICS acts as an intermediate management step between trusted agents PKI and end entities . is a flow diagram of an illustrative automated provisioning process with an ICS . Broken lines indicate on what server the blocks of the process may take place in the implementation shown however other implementations are possible.

At block BOS receives an inventory from host after the host initially powers up and executes an assimilation module . At block BOS also updates HMDB to set a host status indicating that assembly is in progress to set a hardware identifier HWID and to set a provisioning expiration date. At block BOS sends the host a boot workflow.

At block host processes the boot workflow and initiates the OSIM which in turn requests an OS image from the OSIS . At block OSIS retrieves the HWID from the HMDB . At block OSIS builds an OS image which incorporates this HWID and provides the OS image to host . At block host begins the installation of the OS image. When the installation has progressed sufficiently to allow local storage at block host may access and store the HWID locally in a file.

For additional security the OSIM may close all network interfaces on the host during the deployment process at block except for a control channel. This control channel permits communication with the BOS . Where the OSIM and host are virts on the same physical host the control channel between those virts may be considered highly secure.

Similar to above where high security is called for a host may be disallowed from self generating a CSR. In such a high security environment using virtualized server implementations host may request a CSR from a trusted agent which is a virtualized instance on the same physical hardware the virtualized host is executing on. Thus the communications host and trusted agent would use control channel between virts and be considered highly secure.

At block host starts the CMSM upon boot of the OS. At block when the CMSM on host determines no valid certificates are available a new certificate enrollment process may be initiated.

At block ICS receives an enrollment request from host and maps the host to a certificate profile. The certificate profile describes what certificate types are available to a host as certificate status such as what certificates have been issued pending or revoked.

At block ICS checks validity of the host to determine if the status of host indicates an enrollment is in progress and the request is within the provisioning expiration date. This is in contrast to the process of where a CAS performs the verification. When host is valid block requests a PIN from PKI .

At block PKI generates and provides a PIN to ICS for use by host . This PIN comprises a one time password and may be valid for a specified period of time. Use of a PIN provides increased security because it is specifically generated for a given host and may contain a built in expiration date. Within PKI as described above the PIN request may be processed by a CAS a RAS or other PKI component.

At block ICS maps a certificate authority CA or registration authority RA to host and sets status in HMDB indicating the new enrollment request and PIN is approved. This mapping may include multiple possible CA s or RA s to provide for redundancy in the event of a CA or RA failure. At block ICS provides the PIN and CA RA information to host .

At block host generates a private key. At block host uses the private key and the CA RA information received from ICS to obtain a certificate from a CA such as CAS . Once obtained at block host may generate and provide a CSR to PKI .

At block PKI verifies the mapping of the PIN and hostname to confirm validity of the CSR provided by host . When valid at block PKI provides a signed public key certificate to host .

At block host stores the signed public key certificate provided by PKI and provides a notice of issuance to ICS . At block ICS updates status of the host in HMDB to indicate enrollment of host is complete.

At host initiates a new enrollment process with ICS . At ICS maps the host to certificate profile in HMDB . At ICS checks host validity with PKI . When the host is valid at PKI provides a PIN to ICS . At ICS maps CA RA s to host and sets approval status within HMDB . At ICS provides PIN and CA RA information to host . At host obtains a CA certificate from PKI . At host submits a CSR signed with the obtained CA certificate to PKI . At PKI may determine when the CSR is valid and provide a signed public key certificate to host . At host notifies ICS of issuance of a signed certificate. At ICS updates status of the host in HMDB to indicate enrollment is complete.

Once the initial encryption certificate has been issued the host may need to revoke an existing certificate and be issued a new certificate. This renewal process is now described.

At block host generates a new CSR at the host. At block host signs the new CSR with the current host encryption certificate. At block host sends the signed CSR to CAS .

At block CAS determines if the CSR is signed with host s current certificate. When the CSR is signed with the current certificate for host at block CAS signs a new certificate for host . At block CAS sends the new certificate to host . When CAS at block determines that a CSR is not signed with host s current certificate at block CAS denies the request and may also log the incident and issue an alert for follow up by an administrator. This process helps to tightly control the number of valid encryption certificates which are available at any given time. Any of the processes described in this application may be configured to provide notification to a system administrator should they become interrupted or result in an error state.

At CMSM provides a new CSR signed with the current host certificate to VSM on CAS . At VSM verifies the CSR and passes the CSR to CAM for issuance of an encryption certificate. Verification of identity and host status at CAM as described above in may also take place.

At following issuance by CAM VSM provides a new certificate to CMSM . At CMSM stores the new certificate in LCSM and may revoke the current certificate. At CMSM may provide an acknowledgement of receipt of the new certificate to VSM . At VSM then updates the host certificate status in HMDB and may revoke or allow the current certificate to expire.

As described above once an initial encryption certificate has been issued the host may need to renew a certificate. is a flow diagram of an alternative illustrative automated certificate renewal process with ICS. Broken lines indicate on what server the blocks of the process may take place in the implementation shown however other implementations are possible.

At block host initiates a certificate renewal. At block host signs a new CSR with the current host certificate. At block host provides the signed CSR to ICS .

At block ICS determines if the host certificate used to sign the CSR from host is valid. When the certificate is valid at block the ICS may generate a Certificate Management over Cryptographic Message Syntax CMC message as defined by the Internet Engineering Task Force Request for Comments and and update the status in HMDB to indicate that renewal is in progress.

At block CAS processes the CMC and may sign new certificate for host . At block CAS provides the signed new certificate to host . At block host provides a notice of issuance of certificate to ICS . At block ICS updates the certificate status in HMDB to indicate the certificate has been successfully renewed.

At host sends a CSR signed with current host certificate to ICS . At ICS provides a CMC to CAS . At ICS updates status in HMDB to indicate renewal of certificate is pending. At upon validation of CSR CAS provides a signed certificate to host . At host notifies ICS of successful certificate issuance. At ICS updates host certificate status to indicate renewal is complete.

It is occasionally necessary to revoke or invalidate an existing certificate. Revocation of a certificate may be initiated by decommissioning security policies security breach etc. After revocation a certificate is no longer valid.

At block ICS receives a call to revoke one or more host certificates held by a host. At ICS may verify the caller. When the call is verified at block ICS may query a certificate authority for valid certificates mapped to the host.

At block CAS may receive and process the query. At block CAS provides the certificates resulting from the query to ICS . At block ICS may issue a CMC revocation to the certificate authority. At block CAS the certificate authority in this figure acts on the CMC revocation and revokes the certificates. At block ICS updates the certificate status for the host in HMDB .

At the call to revoke a host certificate is presented to ICS . When the call is validated at ICS queries the CAS for valid certificates assigned to the host. At CAS provides the certificates to ICS . At ICS issues a CMC revocation to CAS . At ICS updates the certificate status in HMDB to indicate the certificates have been revoked.

Although specific details of illustrative methods are described with regard to the figures and other flow diagrams presented herein it should be understood that certain acts shown in the figures need not be performed in the order described and may be modified and or may be omitted entirely depending on the circumstances. As described in this application modules and engines may be implemented using software hardware firmware or a combination of these. Moreover the acts and methods described may be implemented by a computer processor or other computing device based on instructions stored on memory the memory comprising one or more computer readable storage media CRSM .

The CRSM may be any available physical media accessible by a computing device to implement the instructions stored thereon. CRSM may include but is not limited to random access memory RAM read only memory ROM electrically erasable programmable read only memory EEPROM flash memory or other solid state memory technology compact disk read only memory CD ROM digital versatile disks DVD or other optical disk storage magnetic cassettes magnetic tape magnetic disk storage or other magnetic storage devices or any other medium which can be used to store the desired information and which can be accessed by a computing device.

Furthermore while this application has been discussed in the context of certificate authentication other implementations are possible. For example Kerberos or other computer network authentication protocols may be utilized instead of or in addition to certificate authentication.

