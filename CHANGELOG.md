commit a1fd26aed801dff0d95f0f71d68ff4e0f736dae8
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Wed May 6 13:57:06 2020 -0400

    Added ability to skip networking CNI install
    
    This may have some value in whether or not the need to add manually
    (possibly) the network constructs. May need to revisit.

commit da7741711507f7b8a39314e9082dc4437a4ecf82
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Mon Apr 27 17:03:35 2020 -0400

    Updated repo usage and info

commit df096446b327ac8ed4317b50db1ab9fefe6422ef
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Mon Apr 27 17:03:22 2020 -0400

    Fixed helm version check

commit e54a011fe17dec210355cf4a36bf52f6de6fb2d1
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Mon Apr 27 17:02:17 2020 -0400

    Fixed tags for various tasks

commit 0d60bd406d886fdd918545b4eacc39f01de3e22b
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Mon Apr 27 17:00:05 2020 -0400

    Updated link to dashboard

commit 75f5eabc33210e7513a9a858fe08ec897c977c07
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Mon Apr 27 15:28:54 2020 -0400

    Cleaned up repo info a bit
    
    Still needs more

commit 79e47c45d4fe0b3203a61cc453b3a06d9a261d81
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Mon Apr 27 15:28:28 2020 -0400

    Added NFS server/client roles to requirements

commit 65390c0b641d52211d9da23c229735f55654e37e
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Mon Apr 27 15:28:11 2020 -0400

    Tags should not have bool checks

commit 112e801a9e88374105db0a761dfc5edfd8c2c97d
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Mon Apr 27 15:27:53 2020 -0400

    Added Ubuntu 18.04 support

commit 4c97462d68abae66560c7d44865557ee93d89e21
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Mon Apr 27 15:27:34 2020 -0400

    Changed K8s version to 1.17.5
    
    - Had issues going to 1.18.0 for now

commit 6f7bcbc3a157e12a4172f28ab1e58420c2dc57e6
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Mon Apr 27 15:26:54 2020 -0400

    Changed Helm install from v2 to v3

commit 293e091849815be2e29c8bc948d13e4fa4cefc8d
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Mon Apr 27 15:26:10 2020 -0400

    Cleaned up lingering commented out tasks

commit f971b4fda68e9a77b20d1904a69d932ba4680b5c
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Mon Apr 27 15:24:59 2020 -0400

    Changed with_items to loop

commit 83a59aef00ae689338270141e887a55cf5b913f0
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Mon Apr 27 15:20:49 2020 -0400

    Updated Vagrant testing for role
    
    This is now updated and tested for Vagrant
    - Spins up a 3-node cluster
    - Spins up a nfs server for persistent volume testing
    - MetalLB deployment is semi functional

commit 030779ae02e7adab5131b60c9d92f369780b96c9
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Sun Apr 26 20:42:23 2020 -0400

    Updated additional roles for Vagrant testing

commit 6f78cb8a75914ad60e2fb9aad539836cd3544381
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Sun Apr 26 20:41:23 2020 -0400

    Moved remaining playbooks to the playbooks dir

commit 4ac58837d082a5948ace0fa7ff9215ffb41db73f
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Fri Apr 24 10:00:36 2020 -0400

    Reorganized Vagrant testing structure

commit 36624a54c1449c0236ce4fe50e7d76831241f2cf
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Thu Apr 23 12:38:53 2020 -0400

    Updated roles to latest

commit 30df0c22189275cc8846a96ac5edb017038ee04e
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Mon Sep 30 17:49:29 2019 -0400

    Cleaned up code
    
    - Cleaned up formatting
    - Cleaned up conditionals

commit b2fe27b6728e17eac5aabdd9d37daaeaa9e215b9
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Thu Sep 5 15:57:03 2019 -0400

    Updated Ansible roles

commit 60e9e4df93ae4de5137f85c5c5e6df88858ab09d
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Thu Sep 5 15:45:28 2019 -0400

    Updated version to 1.13.5

commit 11e140daa06aa04c1ff52b5a397da01a8de97340
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Thu Sep 5 15:44:59 2019 -0400

    Increased number of vCPU to 2 as pre-flight

commit 85ff1e878dfbe0690233e00286b8c2cff7e9b5c0
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Thu Sep 5 15:44:40 2019 -0400

    Updated Ansible roles

commit 0883d7439f6f8cf44d4b9eb1d864fc41d9716abe
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Thu Sep 5 14:58:27 2019 -0400

    Updated version to 1.12.7

commit 30faa2a2c3ce661a9c00312921050c06339492b4
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Thu Sep 5 14:02:20 2019 -0400

    Changed Supported Version
    
    - K8s (1.11.10)
    - K8s-CNI (0.7.5)

commit 7192a35a75bef6313d3b3212d2d92997f30745a1
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Thu Sep 5 00:12:52 2019 -0400

    Cleaned up apt tasks - Loops

commit ca67aec4bf8f84e996206c733a9f4517946a69a0
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Thu Sep 5 00:12:13 2019 -0400

    Cleaned up and added host_vars

commit cb2a5bd1a8f6158e7f551d53fee53e6ae8d7761e
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Thu Sep 5 00:12:00 2019 -0400

    Added pinned version of CNI

commit 9a6eb80936100cdcf7219c4b22966147efebba22
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Thu Sep 13 22:05:09 2018 -0400

    Added Helm install flag for true to install

commit 7f71c682673ce72bb56bff90c5236e926c8d59c7
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Thu Sep 13 22:04:45 2018 -0400

    Updated Helm version and K8s version

commit 19ff163692a726e04e17451ebce961e8168f6c49
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Thu May 10 15:02:02 2018 -0400

    Added playbook to reset k8s cluster

commit 9322eecc24da386405ed7c6b5644ae5af8fae4e4
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Thu May 10 15:01:45 2018 -0400

    Changed Helm version

commit a72ae0331294d5fda4a246eab747769df30880b1
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Thu May 10 14:08:53 2018 -0400

    Resolved Helm install when choosing to install as part of provisioning

commit 098363b687361f315ab387eab73c4fc4493fa2c1
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Thu May 3 08:11:43 2018 -0400

    Implemented ability to pin a specific version of K8s to install.
    
    Resolves #11

commit c05d0d97dd9a72f72f23943d25f1212b714f83f4
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Thu Feb 15 21:20:09 2018 -0500

    Added check for CoreDNS in addition to kube-dns

commit fcaf1a5022f3ddc5b504509e26cfe3f40bfcd9c1
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Mon Feb 12 01:06:48 2018 -0500

    Added functionality to install helm for architecture other than amd64

commit aef065200a13fd67bdce74e27982a3075031b321
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Fri Feb 9 21:40:25 2018 -0500

    Updated and fixed Weave network install

commit 298d24b842e6d9366022ce3ab463af6e7e786178
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Wed Feb 7 14:16:23 2018 -0500

    Fixed issue with capturing token post initial cluster provisioning.

commit 9b1ea144de9f33f5d583429a773e4d079ebc8d1e
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Tue Feb 6 12:03:48 2018 -0500

    Added become: true due to issue when shell does not find route command

commit 1cad3861149fa70d2e7e9219a93937593c616f7f
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Sat Jan 6 01:47:36 2018 -0500

    Fixed subsequent execution issue with properly displaying dashboard info

commit 3ff333c89fd0b20ada5864d3e7a6f74f470f3b78
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Wed Jan 3 01:10:28 2018 -0500

    Updated repo/usage info/examples

commit f499e03e18a52540e3578949ad6a8e29b8113dd4
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Wed Jan 3 01:10:16 2018 -0500

    Fixed missing tag for dashboard

commit ee56c0952fdb334855083d8cb33fbf7fb3bd7f1e
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Wed Jan 3 01:09:30 2018 -0500

    Resolves #10

commit ae43f40549e0a63f1e48a5ef4b1127b6ff829697
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Sun Dec 31 09:31:17 2017 -0500

    Added back no logging on joining cluster
    
    I disabled this for debugging of issue #10 but forgot to re-enable it on
    previous commit.

commit 20c84cca73f41726adbbc63a38a3642f143ddc6e
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Sun Dec 31 09:25:21 2017 -0500

    Cleaned up formatting of vars/tasks

commit 7f236a378ddb75b723d76547779d2e4c43ebbf59
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Sun Dec 31 09:23:48 2017 -0500

    Updated roles
    
    Signed-off-by: Larry Smith Jr <mrlesmithjr@gmail.com>

commit b40a6bfb208d9efeabd7643b3cd4d2382cd082cb
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Sun Dec 31 09:23:31 2017 -0500

    Fixed Docker install version

commit 403814f9799e5833314d121f4ca31582b425e85a
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Sun Dec 31 09:23:09 2017 -0500

    Updated/cleaned up repo info

commit dbd85d12f9ce2f12f4e5eea891173047eb41614e
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Thu Dec 21 07:29:33 2017 -0500

    Updated licensing

commit 27825e13cdb1e32684779df70d887adaf7c46588
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Thu Dec 21 07:26:01 2017 -0500

    Create LICENSE

commit 1bb1ae761facf4e23ca17c08f90f3cae450edf90
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Wed Nov 22 10:57:21 2017 -0500

    Updated roles for Vagrant
    
    Signed-off-by: Larry Smith Jr <mrlesmithjr@gmail.com>

commit 0a83c8cc4fa6edc355636e6ef857c6e04929a198
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Wed Nov 22 10:55:34 2017 -0500

    Cleaned up k8s role for Vagrant
    
    Signed-off-by: Larry Smith Jr <mrlesmithjr@gmail.com>

commit 41a40db2593844dca3bdc117ae7f9b7dd4bd6a49
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Wed Nov 22 10:47:16 2017 -0500

    Fixed dashboard install and issue with creating cluster
    
    Cluster was failing to initialize because of swap being enabled on
    hosts.

commit f156a182bbe947b42ab7140d7ede5b986c65603c
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Thu Apr 27 15:53:04 2017 -0400

    Fixed dashboard retrieval on provision
    
    Signed-off-by: Larry Smith Jr <mrlesmithjr@gmail.com>

commit 43b17ea8c922304170b0212481b0375f19a8348d
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Wed Apr 26 08:10:22 2017 -0400

    Fixed not being able to report dashboard link
    
    Signed-off-by: Larry Smith Jr <mrlesmithjr@gmail.com>

commit 06a9a2aa8c1c48610a1e099ce9c7372b5ed62acb
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Tue Apr 25 22:40:47 2017 -0400

    Updated roles and playbook
    
    Signed-off-by: Larry Smith Jr <mrlesmithjr@gmail.com>

commit 032de8fca4722d04766b00e5babf93454fa65576
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Tue Apr 25 22:38:44 2017 -0400

    Updated and added more functionality
    
    Signed-off-by: Larry Smith Jr <mrlesmithjr@gmail.com>

commit 840cdef1cf370fdf5798f91ba394d2bcea022235
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Tue Apr 25 17:19:23 2017 -0400

    Added ability to capture running pods and info on them presented in JSON format
    
    Signed-off-by: Larry Smith Jr <mrlesmithjr@gmail.com>

commit f60a090da9dc191c6032888a6c86ac4ad87f8909
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Tue Apr 25 13:07:38 2017 -0400

    Added Helm install ability
    
    Signed-off-by: Larry Smith Jr <mrlesmithjr@gmail.com>

commit c36cfffca143dd2b49d2f860fa7a87d0bd4f1a52
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Tue Apr 25 10:48:05 2017 -0400

    Fixed Weave-Net link
    
    Signed-off-by: Larry Smith Jr <mrlesmithjr@gmail.com>

commit 4cc8c19e0a00ff930f333811781bb48add592d3f
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Tue Apr 25 10:42:49 2017 -0400

    Added info on resetting cluster
    
    Signed-off-by: Larry Smith Jr <mrlesmithjr@gmail.com>

commit 4fd7af3ea5111055471966d11b63417687a2f7b4
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Tue Apr 25 10:33:40 2017 -0400

    Updated with Vagrant environment
    
    Signed-off-by: Larry Smith Jr <mrlesmithjr@gmail.com>

commit 2f5e24030133dcf58fc4b0423c0f2918066f38d4
Author: Larry Smith Jr <mrlesmithjr@gmail.com>
Date:   Tue Apr 25 10:11:34 2017 -0400

    first commit
