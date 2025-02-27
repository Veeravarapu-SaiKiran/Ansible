ansible centos1 -m setup -a "gather_subset=network"
ansible centos1 -m setup -a "gather_subset=!all,!min,network"
ansible centos1 -m setup -a "filter=ansible_distribution,ansible_memfree_mb"
ansible centos1 -m setup -a "filter=ansible_mem*"


gather_subset Options

1. all  ->  Gather all available facts.
2. minl  ->  Gather minimal facts (OS, distribution, Python version).
3. hardware	 -> Collects CPU, memory, disk, and hardware-related facts.
4. network	->  Collects network interfaces, IP addresses, and routes.
5. virtual	->  Detects if the system is virtualized (VMware, AWS, Docker, etc.).
6. ohai	 ->  Uses Ohai to gather additional system facts (requires Ohai installed).
7. facter	->  Uses Facter (from Puppet) to collect additional facts.