OSINT and Domain Relationship Analysis Using Maltego

## Objective

To use Maltego Desktop to investigate a domain entity, explore available information-gathering transforms, and visualise relationships between domain-related entities.

## Tool Used

- **Tool:** Maltego Desktop 4.14.0
- **Operating System:** Kali Linux (running in Oracle VirtualBox)
- **Target domain:** `networkwalks.com`
- **Entity type:** Domain
- **Transform category explored:** DNS and WHOIS-related transforms

## Activities Performed

### 1. Launching Maltego

I launched Maltego from the Kali Linux terminal using:

```bash
maltego
```

The application started successfully and displayed the Maltego Desktop interface.

### 2. Creating a Domain Entity

I created a new graph and added a **Domain** entity with the value:

```text
networkwalks.com
```

This domain entity served as the starting point for the investigation.

### 3. Exploring Available Transforms

I explored the available Maltego transforms for gathering information about the domain.

The visible transform options included:

- Extract Translation to Phrase
- To DNS Name – MX (mail server)
- To DNS Name – NS (mail server)
- To DNS Name – SOA (Start of Authority)
- To DNS Name – SPF (sender policy framework)
- To DNS Name (Attempt zone transfer)
- To DNS Name (Find common DNS names)
- To DNS Name (Using Name Schema dictionary)
- To Domains (DNS)
- To Email address (From WHOIS info)

These were the transforms visible in the application. The screenshots specifically provide evidence of the WHOIS-to-email-address transform being executed.

### 4. Executing the WHOIS-to-Email Transform

I ran the following available transform from the domain entity:

**To Email address [From whois info]**

The transform completed successfully, and the graph displayed an email-address entity:

```text
abuse@godaddy.com
```

The graph showed a relationship between:

- Domain: `networkwalks.com`
- Email address: `abuse@godaddy.com`

The transform output indicated that the operation completed in approximately 3.8 seconds.

This result represents an email address returned by the WHOIS-related transform. It should not be interpreted as proof that the address belongs to the domain owner or that it is a personal contact address.

## Findings and Observations

| Area | Observation |
|---|---|
| Application | Maltego Desktop 4.14.0 |
| Operating system | Kali Linux |
| Starting entity | `networkwalks.com` |
| Entity type | Domain |
| Transform executed | To Email address [From whois info] |
| Resulting entity | `abuse@godaddy.com` |
| Graph relationship | Domain connected to an email-address entity |
| Other transforms | DNS and domain-related transform options were visible for further investigation |

The exercise demonstrated how Maltego can represent information gathered from different sources as entities and relationships in a visual graph.

## Analysis

Maltego provides a graphical approach to Open-Source Intelligence (OSINT) investigations. Instead of viewing every finding as an isolated piece of information, investigators can use entities and relationships to organise and explore connections.

In this exercise:

1. The domain `networkwalks.com` was used as the starting entity.
2. Available transforms provided options for investigating DNS and WHOIS-related information.
3. The WHOIS-to-email-address transform returned `abuse@godaddy.com`.
4. Maltego displayed the domain and email address as connected entities in the graph.

The result illustrates how domain-related information can be expanded into additional entities for further investigation.

It is important to distinguish between a transform option being available and a transform actually being executed. The screenshots confirm the WHOIS-to-email result, but do not provide completed outputs for the other listed DNS transforms.

## Challenges and Solutions

### Challenge 1: Understanding Maltego entities and transforms

Maltego uses entities to represent information and transforms to discover relationships or retrieve additional data. Understanding how these components work together was an important part of the exercise.

**Solution:** I started with a single Domain entity and explored the available transforms to understand how additional information could be associated with it.

### Challenge 2: Interpreting transform results

The email address returned by the WHOIS-related transform needed to be interpreted carefully. A returned email address does not automatically establish ownership or identify a domain administrator.

**Solution:** I documented the result as an email address returned by the transform and avoided making unsupported claims about its ownership or purpose beyond the visible result.

## Lessons Learned

- Maltego can be used for visual OSINT investigations.
- Entities represent objects such as domains and email addresses.
- Transforms help discover additional information and relationships.
- DNS and WHOIS information can support domain investigations.
- Graph visualisation makes it easier to organise and interpret relationships.
- Transform results should be verified and interpreted in context.
- An available transform should not be reported as completed unless its execution and output have been confirmed.

## Evidence

<img width="2736" height="1824" alt="maltego" src="https://github.com/user-attachments/assets/dfb46ebd-c726-426d-aa64-de254f7065d9" />
01-maltego-launch-kali

<img width="2736" height="1824" alt="maltego01" src="https://github.com/user-attachments/assets/ed1004aa-0ead-43fa-93b2-73347cfbbc00" />
02-maltego-domain-transforms

<img width="2736" height="1824" alt="maltego001" src="https://github.com/user-attachments/assets/bccb52e9-610d-448a-8be9-ff744bd36c8b" />
03-maltego-domain-entity

<img width="2736" height="1824" alt="maltego1" src="https://github.com/user-attachments/assets/85c639f2-aa45-40b6-bcf4-53ebcdddcf0a" />
04-maltego-whois-email-relationship



## Conclusion

This exercise introduced me to Maltego Desktop and its application in OSINT and domain investigations. By creating a domain entity for `networkwalks.com` and executing a WHOIS-related transform, I was able to retrieve an email-address entity and visualise its relationship with the domain.

The exercise strengthened my understanding of graphical reconnaissance, entity relationships, WHOIS-based information gathering and the importance of accurately interpreting OSINT results.

**Disclaimer:** This exercise is documented for educational purposes. Findings are based on the supplied Maltego screenshots and should not be interpreted as confirmation of a security vulnerability or a verified ownership relationship.

