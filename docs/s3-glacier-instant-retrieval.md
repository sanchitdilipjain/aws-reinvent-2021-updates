## Amazon Simple Storage Service (S3) Glacier Instant Retrieval

**What is Amazon Simple Storage Service (S3)?**
- Amazon S3 is one of the main building blocks of AWS. It’s advertised as ”infinitely scaling” storage. It’s widely popular and deserves its own section
- S3 provides unlimited storage space and works on the pay-as-you-use model. Service rates get cheaper as the usage volume increases
- Amazon S3 allows people to store objects (files) in “buckets” (directories). S3 resources for e.g. buckets and objects are private by default

**What are different storage class?**
- Amazon S3 offers a range of storage classes that you can choose from based on the data access, resiliency, and cost requirements of your workloads. 
- S3 storage classes are purpose-built to provide the lowest cost storage for different access patterns

  <img src="images/s3-glacier-instant/image1.png" class="inline" width="700" height="500"/>

**Introduction to Amazon Simple Storage Service (S3) Glacier Instant Retrieval**

- Amazon Simple Storage Service (S3) Glacier Instant Retrieval is an archive storage class that delivers the lowest-cost storage for long-lived data that is rarely accessed and requires retrieval in milliseconds. 
- With Amazon S3 Glacier Instant Retrieval, you can save up to 68% on storage costs compared to using the S3 Standard-Infrequent Access (S3 Standard-IA) storage class, when your data is accessed once per quarter. 
- S3 Glacier Instant Retrieval delivers the fastest access to archive storage, with the same throughput and milliseconds access as the S3 Standard and S3 Standard-IA storage classes. S3 Glacier Instant Retrieval is designed for 99.999999999% (11 nines) data durability and 99.9% availability by redundantly storing data across multiple physically separated Availability Zones (AZs). 
- It’s designed for rarely accessed data that still needs immediate access in performance-sensitive use cases like image hosting, online file-sharing applications, medical imaging and health records, news media assets, and genomics.
- **Benefits:**

  - **Retrievals in milliseconds**. S3 Glacier Instant Retrieval delivers milliseconds retrieval for archives that need immediate access, such as medical images, news
  media assets, and user-generated content. For applications that need fast access to your archive data, S3 Glacier Instant Retrieval delivers low-latency and
  high-throughput performance.
  - **Unmatched durability and scalability**. S3 Glacier Instant Retrieval runs on the world’s largest global cloud infrastructure with virtually unlimited scalability
  and is designed for 99.999999999% (11 nines) durability. Data is automatically distributed across multiple AZs that are geographically separated within a
  Region.
  - **Most comprehensive security and compliance capabilities**. S3 Glacier Instant Retrieval offers integration with AWS CloudTrail to log, monitor, and retain
  storage API call activities for auditing, and it supports three different forms of encryption. S3 also supports security standards and compliance certifications, including SEC Rule 17a-4, PCI-DSS, HIPAA/HITECH eligibility, FedRAMP, EU GDPR, and FISMA. S3 Object Lock enables WORM storage capabilities, helping satisfy compliance requirements for virtually every regulatory agency around the globe.
  - **Easily manage your data lifecycle**. Cost-effectively manage data through its lifecycle across the S3 storage classes, which share the S3 APIs. You can use S3 Lifecycle to easily transition your data to lower-cost storage classes, as the data becomes less frequently accessed—without performing any data migration.
  - **Low cost**. S3 Glacier Retrieval is the lowest-cost archive storage with milliseconds retrieval for rarely accessed data. It’s ideal for data that’s accessed once or twice per quarter, and requires immediate access.
- **Use cases:**

  - **Media asset workflows**. Media and entertainment assets, such as video and news footage, require durable storage and can grow to many petabytes over
  time. Much of this data needs to be available immediately for breaking news events, video rendering, or content development. The S3 Glacier Instant Retrieval storage class allows you to archive older media content affordably while still making it available in milliseconds when it's needed. To save even more on storage costs for media archives that don't require milliseconds access, you can use S3 Glacier Flexible Retrieval (formerly S3 Glacier) or S3 Glacier Deep Archive.
  - **Healthcare information archiving**. Hospital systems need to retain petabytes of patient records (such as LIS, PACS, and EHR) for decades to meet regulatory requirements. The S3 Glacier Instant Retrieval storage class is ideal for medical images or genomics, where milliseconds retrieval is required.
  - **Scientific data analytics**. Research organizations generate, analyze, and archive vast amounts of data, such as for genomics or to train machine learning (ML) models. With the S3 Glacier Instant Retrieval storage class, you avoid the complexities of hardware and facility management and capacity planning, with the lowest-cost storage and milliseconds retrieval.

- **Performance across the S3 Storage Classes**
  
    <img src="images/s3-glacier-instant/image2.png" class="inline" width="800" height="425"/>

