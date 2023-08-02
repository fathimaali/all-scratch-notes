https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html 

![[Pasted image 20230426134912.png]]

When you launch a new EC2 instance, the EC2 service attempts to place the instance in such a way that all of your instances are spread out across underlying hardware to minimize correlated failures. You can use _placement groups_ to influence the placement of a group of _interdependent_ instances to meet the needs of your workload. Depending on the type of workload, you can create a placement group using one of the following placement strategies:

-   **Cluster** – packs instances close together inside an Availability Zone. This strategy enables workloads to achieve the low-latency network performance necessary for tightly-coupled node-to-node communication that is typical of high-performance computing (HPC) applications.
	![[Pasted image 20230426135227.png]]

-   **Spread** – strictly places a small group of instances across distinct underlying hardware to reduce correlated failures.
	![[Pasted image 20230426135420.png]]
	
-   **Partition** – spreads your instances across logical partitions such that groups of instances in one partition do not share the underlying hardware with groups of instances in different partitions. This strategy is typically used by large distributed and replicated workloads, such as Hadoop, Cassandra, and Kafka.
	![[Pasted image 20230426135644.png]]

can create Placement Groups from -> 

![[Pasted image 20230426135928.png]]

when Launching Instance -> Advance Settings has : 
![[Pasted image 20230426140004.png]]
