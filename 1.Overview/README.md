## 1. Overview

### 1. Understanding the difference between a region, an Availiability Zone(AZ) and an Edge Location

- A Region is a physical location in the world which consists of two or more Availiability Zones(AZ's)
- An AZ is one or more discrete data centers, each with redundant power, networking and connectivity, housed in seperate facilites.
- Edge Locations are endpoints for AWS which are used for caching content. Typically the consists of CloudFront, Amazon's Content Delivery Network(CDN)

---

#### Q1. What is an Amazon VPC?

- Virtual Private Cloud

#### Q2. An AWS VPC is a component of which group of AWS services?

- Networking Services

#### Q3. What does an AWS Region consist of?

- A distinct location within a geograpic area designed to provide high availability to a specific geography.
  Each region is a seperate geographic area. Each region has multiple, isolated locations known as Availability Zones.

#### Q4. Which statement best describes Availability Zones?

- Distict locations from within an AWS region that are engineered to be isolated from failures.
  An Availability Zone(AZ) is a distinc location within an AWS Region. Each Region comporise at least two AZs.

#### Q5. What is an AWS region?

- A region is a geographical area divided into Availability Zones. Each region contains at least two Availability Zones.

#### Q6. Which of the following is correct?

- \# of Edge Locations > \# of Availability Zones > \# of Regions
  The number of Edge Locations is greater than the number of Availability Zones, which is greater than the number of Regions.

#### Q7. In which of the following is CloudFront content cached?

- Edge Location
  CloudFront content is cached in Edge Locations.
