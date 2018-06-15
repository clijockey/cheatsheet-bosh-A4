# cheatsheet-bosh-A4
Bosh CheatSheets In A4

<a href="https://github.com/DennyZhang?tab=followers"><img align="right" width="200" height="183" src="https://raw.githubusercontent.com/USDevOps/mywechat-slack-group/master/images/fork_github.png" /></a>

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)

[![LinkedIn](https://raw.githubusercontent.com/USDevOps/mywechat-slack-group/master/images/linkedin_icon.png)](https://www.linkedin.com/in/dennyzhang001) <a href="https://www.dennyzhang.com/slack" target="_blank" rel="nofollow"><img src="http://slack.dennyzhang.com/badge.svg" alt="slack"/></a> [![Github](https://raw.githubusercontent.com/USDevOps/mywechat-slack-group/master/images/github.png)](https://github.com/DennyZhang)

File me [tickets](https://github.com/DennyZhang/cheatsheet-bosh-A4/issues) or star [the repo](https://github.com/DennyZhang/cheatsheet-bosh-A4).

Printable version on A4 page: [cheatsheet-bosh-A4.pdf](cheatsheet-bosh-A4.pdf)

<a href="https://www.dennyzhang.com"><img align="right" width="185" height="37" src="https://raw.githubusercontent.com/USDevOps/mywechat-slack-group/master/images/dns_small.png"></a>

See more CheatSheets from Denny: [here](https://github.com/topics/denny-cheatsheets)

- Query status

| Name                        | Command                                    |
| :-------------------------- | ------------------------------------------ |
| List all bosh deployments   | `bosh deployments`                         |
| Download log files          | `bosh -d $deployment_id logs`              |
|                             | `bosh cloud-config`                        |
|                             | `bosh configs`                             |
| List environment            | `bosh env`                                 |
| List vms                    | `bosh vms`                                 |
| Get vms per deployment      | `bosh -e $env -d $deployment vms`          |
|                             | `bosh instances`                           |
| Cloud consistency check     | `bosh cloud-check -d $deployment`          |
| Show deployment manifest    | `bosh manifest -d $deployment`             |
| List disks                  | `bosh disks -o`                            |

- Tasks

| Name                      | Command                                       |
| :------------------------ | ------------------------------------------    |
| List recent tasks         | `bosh tasks --recent 10`                      |
| Attach to current task    | `bosh task -a`                                |
| Get task by id            | `bosh task $id`                               |
|                           | `bosh events`                                 |
| SSH to vm                 | `bosh ssh -d $deployment_name $instance_name` |
|                           | `bosh logs -d $deployment_name`               |

- Misc

| Name                  | Command                                                        |
| :-------------------- | -------------------------------------------------------------  |
| Install bosh          | `apt install bosh-cli`                                         |
| delete vm             | `bosh delete-vm -d service-instance_c4b06291-XXX 35043957-XXX` |
| ssh to vm             | `bosh -e 192.168.30.52 -d $deployment ssh $vm`                 |

- Online Help Usage
```
kubo@jumper:~$ bosh --help
Usage:
  bosh [OPTIONS] <command>

Application Options:
  -v, --version          Show CLI version
      --config=          Config file path (default: ~/.bosh/config) [$BOSH_CONFIG]
  -e, --environment=     Director environment name or URL [$BOSH_ENVIRONMENT]
      --ca-cert=         Director CA certificate path or value [$BOSH_CA_CERT]
      --sha2             Use SHA256 checksums [$BOSH_SHA2]
      --parallel=        The max number of parallel operations (default: 5)
      --client=          Override username or UAA client [$BOSH_CLIENT]
      --client-secret=   Override password or UAA client secret [$BOSH_CLIENT_SECRET]
  -d, --deployment=      Deployment name [$BOSH_DEPLOYMENT]
      --column=          Filter to show only given column(s)
      --json             Output as JSON
      --tty              Force TTY-like output
      --no-color         Toggle colorized output
  -n, --non-interactive  Don't ask for user input [$BOSH_NON_INTERACTIVE]

Help Options:
  -h, --help             Show this help message

Available commands:
  add-blob               Add blob                                           https://bosh.io/docs/cli-v2#add-blob
  alias-env              Alias environment to save URL and CA certificate   https://bosh.io/docs/cli-v2#alias-env
  attach-disk            Attaches disk to an instance                       https://bosh.io/docs/cli-v2#attach-disk
  blobs                  List blobs                                         https://bosh.io/docs/cli-v2#blobs
  cancel-task            Cancel task at its next checkpoint                 https://bosh.io/docs/cli-v2#cancel-task (aliases: ct)
  clean-up               Clean up releases, stemcells, disks, etc.          https://bosh.io/docs/cli-v2#clean-up
  cloud-check            Cloud consistency check and interactive repair     https://bosh.io/docs/cli-v2#cloud-check (aliases: cck, cloudcheck)
  cloud-config           Show current cloud config                          https://bosh.io/docs/cli-v2#cloud-config (aliases: cc)
  config                 Show current config for either ID or both type and name https://bosh.io/docs/cli-v2#config (aliases: c)
  configs                List configs                                       https://bosh.io/docs/cli-v2#configs (aliases: cs)
  cpi-config             Show current CPI config                            https://bosh.io/docs/cli-v2#cpi-config
  create-env             Create or update BOSH environment                  https://bosh.io/docs/cli-v2#create-env
  create-release         Create release                                     https://bosh.io/docs/cli-v2#create-release (aliases: cr)
  delete-config          Delete config                                      https://bosh.io/docs/cli-v2#delete-config (aliases: dc)
  delete-deployment      Delete deployment                                  https://bosh.io/docs/cli-v2#delete-deployment (aliases: deld)
  delete-disk            Delete disk                                        https://bosh.io/docs/cli-v2#delete-disk
  delete-env             Delete BOSH environment                            https://bosh.io/docs/cli-v2#delete-env
  delete-release         Delete release                                     https://bosh.io/docs/cli-v2#delete-release (aliases: delr)
  delete-snapshot        Delete snapshot                                    https://bosh.io/docs/cli-v2#delete-snapshot
  delete-snapshots       Delete all snapshots in a deployment               https://bosh.io/docs/cli-v2#delete-snapshots
  delete-stemcell        Delete stemcell                                    https://bosh.io/docs/cli-v2#delete-stemcell (aliases: dels)
  delete-vm              Delete VM                                          https://bosh.io/docs/cli-v2#delete-vm
  deploy                 Update deployment                                  https://bosh.io/docs/cli-v2#deploy (aliases: d)
  deployment             Show deployment information                        https://bosh.io/docs/cli-v2#deployment (aliases: dep)
  deployments            List deployments                                   https://bosh.io/docs/cli-v2#deployments (aliases: ds, deps)
  diff-config            Diff two configs by ID                             https://bosh.io/docs/cli-v2#diff-config
  disks                  List disks                                         https://bosh.io/docs/cli-v2#disks
  environment            Show environment                                   https://bosh.io/docs/cli-v2#environment (aliases: env)
  environments           List environments                                  https://bosh.io/docs/cli-v2#environments (aliases: envs)
  errands                List errands                                       https://bosh.io/docs/cli-v2#errands (aliases: es)
  event                  Show event details                                 https://bosh.io/docs/cli-v2#event
  events                 List events                                        https://bosh.io/docs/cli-v2#events
  export-release         Export the compiled release to a tarball           https://bosh.io/docs/cli-v2#export-release
  finalize-release       Create final release from dev release tarball      https://bosh.io/docs/cli-v2#finalize-release
  generate-job           Generate job                                       https://bosh.io/docs/cli-v2#generate-job
  generate-package       Generate package                                   https://bosh.io/docs/cli-v2#generate-package
  help                   Show this help message                             https://bosh.io/docs/cli-v2#help
  ignore                 Ignore an instance                                 https://bosh.io/docs/cli-v2#ignore
  init-release           Initialize release                                 https://bosh.io/docs/cli-v2#init-release
  inspect-release        List release contents such as jobs                 https://bosh.io/docs/cli-v2#inspect-release
  instances              List all instances in a deployment                 https://bosh.io/docs/cli-v2#instances (aliases: is)
  interpolate            Interpolates variables into a manifest             https://bosh.io/docs/cli-v2#interpolate (aliases: int)
  locks                  List current locks                                 https://bosh.io/docs/cli-v2#locks
  log-in                 Log in                                             https://bosh.io/docs/cli-v2#log-in (aliases: l, login)
  log-out                Log out                                            https://bosh.io/docs/cli-v2#log-out (aliases: logout)
  logs                   Fetch logs from instance(s)                        https://bosh.io/docs/cli-v2#logs
  manifest               Show deployment manifest                           https://bosh.io/docs/cli-v2#manifest (aliases: man)
  orphan-disk            Orphan disk                                        https://bosh.io/docs/cli-v2#orphan-disk
  recreate               Recreate instance(s)                               https://bosh.io/docs/cli-v2#recreate
  releases               List releases                                      https://bosh.io/docs/cli-v2#releases (aliases: rs)
  remove-blob            Remove blob                                        https://bosh.io/docs/cli-v2#remove-blob
  repack-stemcell        Repack stemcell                                    https://bosh.io/docs/cli-v2#repack-stemcell
  reset-release          Reset release                                      https://bosh.io/docs/cli-v2#reset-release
  restart                Restart instance(s)                                https://bosh.io/docs/cli-v2#restart
  run-errand             Run errand                                         https://bosh.io/docs/cli-v2#run-errand
  runtime-config         Show current runtime config                        https://bosh.io/docs/cli-v2#runtime-config (aliases: rc)
  scp                    SCP to/from instance(s)                            https://bosh.io/docs/cli-v2#scp
  snapshots              List snapshots                                     https://bosh.io/docs/cli-v2#snapshots
  ssh                    SSH into instance(s)                               https://bosh.io/docs/cli-v2#ssh
  start                  Start instance(s)                                  https://bosh.io/docs/cli-v2#start
  stemcells              List stemcells                                     https://bosh.io/docs/cli-v2#stemcells (aliases: ss)
  stop                   Stop instance(s)                                   https://bosh.io/docs/cli-v2#stop
  sync-blobs             Sync blobs                                         https://bosh.io/docs/cli-v2#sync-blobs
  take-snapshot          Take snapshot                                      https://bosh.io/docs/cli-v2#take-snapshot
  task                   Show task status and start tracking its output     https://bosh.io/docs/cli-v2#task (aliases: t)
  tasks                  List running or recent tasks                       https://bosh.io/docs/cli-v2#tasks (aliases: ts)
  unignore               Unignore an instance                               https://bosh.io/docs/cli-v2#unignore
  update-cloud-config    Update current cloud config                        https://bosh.io/docs/cli-v2#update-cloud-config (aliases: ucc)
  update-config          Update config                                      https://bosh.io/docs/cli-v2#update-config (aliases: uc)
  update-cpi-config      Update current CPI config                          https://bosh.io/docs/cli-v2#update-cpi-config
  update-resurrection    Enable/disable resurrection                        https://bosh.io/docs/cli-v2#update-resurrection
  update-runtime-config  Update current runtime config                      https://bosh.io/docs/cli-v2#update-runtime-config (aliases: urc)
  upload-blobs           Upload blobs                                       https://bosh.io/docs/cli-v2#upload-blobs
  upload-release         Upload release                                     https://bosh.io/docs/cli-v2#upload-release (aliases: ur)
  upload-stemcell        Upload stemcell                                    https://bosh.io/docs/cli-v2#upload-stemcell (aliases: us)
  variables              List variables                                     https://bosh.io/docs/cli-v2#variables (aliases: vars)
  vendor-package         Vendor package                                     https://bosh.io/docs/cli-v2#vendor-package
  vms                    List all VMs in all deployments                    https://bosh.io/docs/cli-v2#vms

Succeeded
```

- bosh delete vm

```
kubo@jumper:~$ bosh vms
Using environment '30.0.X.11' as client 'ops_manager'

Task 291
Task 294
Task 292
Task 293
Task 291 done

Task 292 done

Task 294 done

Task 293 done

Deployment 'XXX-container-service-37f4102408dc7e3b4fcf'

Instance                                                        Process State  AZ    IPs        VM CID                                   VM Type  Active  
XXX-container-service/6245d88f-7d52-4371-a3c2-5dc023c32fe9  running        az-1  30.0.0.12  vm-b27efb7f-c0d8-42e7-bd55-d28f68b10cb7  medium   -  

1 vms

Deployment 'service-instance_1ee08f0f-2e8a-45f9-a1f8-5e0d608225b4'

Instance                                     Process State  AZ    IPs       VM CID                                   VM Type  Active  
master/05e56b86-b650-4ec6-a953-3de9a736517d  running        az-1  40.0.2.2  vm-4bd0dd74-2b13-4062-bc29-d5130f29ed0e  medium   -  
worker/7881dd78-0006-4466-a4bd-ebee59477998  running        az-1  40.0.2.4  vm-d24b71a6-55bd-418e-8694-ed8bb595acd8  medium   -  
worker/adf1ecda-700e-4d52-a675-34c8853fd063  running        az-1  40.0.2.3  vm-73dd78c2-e3d1-4030-9805-7402af9756f8  medium   -  

3 vms

Deployment 'service-instance_c4b06291-ed29-4b5e-89c2-ff35547db2d2'

Instance                                     Process State  AZ    IPs       VM CID                                   VM Type  Active  
master/85496f06-26aa-4dfd-b181-1c6b7e29f655  running        az-1  40.0.1.2  vm-d6938cf5-0349-488b-96c3-9c20784076ea  medium   -  
worker/1f4cc6b9-533a-4edf-bec1-03f2fd402b8d  stopped        az-1  40.0.1.3  vm-00cf6f5b-dfe9-46df-8856-867d5fad4d1b  medium   -  
worker/35043957-97b4-4aa5-bfda-9d495831a7e8  running        az-1  40.0.1.4  vm-b0adf348-3faa-486d-a8f5-a05128932b9a  medium   -  

Succeeded

kubo@jumper:~$ bosh delete-vm -d service-instance_c4b06291-ed29-4b5e-89c2-ff35547db2d2 35043957-97b4-4aa5-bfda-9d495831a7e8
Using environment '30.0.0.11' as client 'ops_manager'

Using deployment 'service-instance_c4b06291-ed29-4b5e-89c2-ff35547db2d2'

Continue? [yN]: y

Task 295
. Done
```

- bosh manifest

```
kubo@jumper:~$  bosh manifest -d service-instance_1ee08f0f-2e8a-45f9-a1f8-5e0d608225b4
Using environment '30.0.0.11' as client 'ops_manager'

Using deployment 'service-instance_1ee08f0f-2e8a-45f9-a1f8-5e0d608225b4'

---
addons:
- name: bosh-dns-aliases
  jobs:
  - name: kubo-dns-aliases
    release: kubo
name: service-instance_1ee08f0f-2e8a-45f9-a1f8-5e0d608225b4
releases:
- name: kubo
  version: 0.16.3
- name: cfcr-etcd
  version: 1.0.2
- name: docker
  version: 31.1.0
- name: pks-nsx-t
  version: 0.9.0
- name: pks-vrli
  version: 0.2.0
- name: syslog-migration
  version: '10'
- name: bpm
  version: 0.4.0
- name: wavefront-proxy
  version: 0.3.0
- name: pks-helpers
  version: 28.0.0
stemcells:
- alias: trusty
  os: ubuntu-trusty
  version: '3541.25'
instance_groups:
- name: apply-addons
  lifecycle: errand
  instances: 1
  jobs:
  - name: apply-specs
    release: kubo
    consumes:
      cloud-provider:
        from: master-cloud-provider
    properties:
      addons-spec: ''
      admin-password: EYX_b6qlSz0Ez7jNDql7GULX
      admin-username: admin
      api-token: "((kubelet-password))"
      authorization-mode: rbac
      tls:
        heapster: "((tls-heapster))"
        influxdb: "((tls-influxdb))"
        kubernetes: "((tls-kubernetes))"
        kubernetes-dashboard: "((tls-kubernetes-dashboard))"
  - name: syslog_forwarder
    release: syslog-migration
    properties:
      syslog:
        address: ''
        ca_cert: 
        migration:
          disabled: false
        permitted_peer: ''
        port: '514'
        tls_enabled: false
        transport: tcp
  vm_type: micro
  stemcell: trusty
  azs:
  - az-1
  networks:
  - name: pks-1ee08f0f-2e8a-45f9-a1f8-5e0d608225b4-cluster-switch
- name: master
  instances: 1
  jobs:
  - name: bpm
    release: bpm
  - name: kube-apiserver
    release: kubo
    consumes:
      cloud-provider:
        from: master-cloud-provider
    properties:
      admin-password: EYX_b6qlSz0Ez7jNDql7GULX
      admin-username: admin
      authorization-mode: rbac
      backend_port: 8443
      kube-controller-manager-password: "((kube-controller-manager-password))"
      kube-proxy-password: "((kube-proxy-password))"
      kube-scheduler-password: "((kube-scheduler-password))"
      kubelet-drain-password: "((kubelet-drain-password))"
      kubelet-password: "((kubelet-password))"
      port: 8443
      route-sync-password: "((route-sync-password))"
      service-account-public-key: "((service-account-key.public_key))"
      tls:
        kubernetes:
          ca: "((tls-kubernetes.ca))"
          certificate: "((tls-kubernetes.certificate))"
          private_key: "((tls-kubernetes.private_key))"
  - name: kube-controller-manager
    release: kubo
    consumes:
      cloud-provider:
        from: master-cloud-provider
    properties:
      api-token: "((kube-controller-manager-password))"
      service-account-private-key: "((service-account-key.private_key))"
      tls:
        kubernetes: "((tls-kubernetes))"
  - name: kube-scheduler
    release: kubo
    properties:
      api-token: "((kube-scheduler-password))"
      tls:
        kubernetes: "((tls-kubernetes))"
  - name: kubernetes-roles
    release: kubo
    consumes:
      cloud-provider:
        from: master-cloud-provider
    properties:
      admin-password: EYX_b6qlSz0Ez7jNDql7GULX
      admin-username: admin
      authorization-mode: rbac
      tls:
        kubernetes: "((tls-kubernetes))"
  - name: etcd
    release: cfcr-etcd
    properties:
      tls:
        etcd:
          ca: "((tls-etcd.ca))"
          certificate: "((tls-etcd.certificate))"
          private_key: "((tls-etcd.private_key))"
        etcdctl:
          ca: "((tls-etcdctl.ca))"
          certificate: "((tls-etcdctl.certificate))"
          private_key: "((tls-etcdctl.private_key))"
        peer:
          ca: "((tls-etcd.ca))"
          certificate: "((tls-etcd.certificate))"
          private_key: "((tls-etcd.private_key))"
  - name: cloud-provider
    release: kubo
    provides:
      cloud-provider:
        as: master-cloud-provider
    properties:
      cloud-provider:
        type: vsphere
        vsphere:
          datacenter: kubo-dc
          datastore: iscsi-ds-0
          insecure-flag: 1
          password: Admin!23
          server: 192.168.111.24
          user: administrator@vsphere.local
          vms: pcf_vms
          working-dir: "/kubo-dc/vm/pcf_vms/aca565a2-93be-4dc2-85dd-d7a512cc0dd7"
  - name: syslog_forwarder
    release: syslog-migration
    properties:
      syslog:
        address: ''
        ca_cert: 
        migration:
          disabled: false
        permitted_peer: ''
        port: '514'
        tls_enabled: false
        transport: tcp
  - name: pks-nsx-t-resource-check
    release: pks-nsx-t
    properties:
      nsx-t-ca-cert: |-
        -----BEGIN CERTIFICATE-----
        MIIDZDCCAkygAwIBAgIGAWP3qchFMA0GCSqGSIb3DQEBCwUAMHMxJDAiBgNVBAMM
        G25zeG1hbmFnZXIucGtzLnZtd2FyZS5sb2NhbDEPMA0GA1UECgwGVk13YXJlMQww
        CgYDVQQLDANDTkExCzAJBgNVBAYTAlVTMQswCQYDVQQIDAJDQTESMBAGA1UEBwwJ
        UGFsbyBBbHRvMB4XDTE4MDYxMzA1NDEyOVoXDTIzMDYxMjA1NDEyOVowczEkMCIG
        A1UEAwwbbnN4bWFuYWdlci5wa3Mudm13YXJlLmxvY2FsMQ8wDQYDVQQKDAZWTXdh
        cmUxDDAKBgNVBAsMA0NOQTELMAkGA1UEBhMCVVMxCzAJBgNVBAgMAkNBMRIwEAYD
        VQQHDAlQYWxvIEFsdG8wggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDZ
        XSVftNvRA2/jQP/UL1ACKb6qR5TDNTE83ehvoZdRZUMra+R89YaS0y0jfaLk4QT0
        jDGU/BPs6iR6HyivWwkwm8SGBxetyPkrR84UFKX9fJideRAU1TaYIc+NEn53hQjC
        e4YR0Be5+U+yT+N8j/J8kirFydKpIk7YHSDIi3Kpa96NeHb12MhzvmEDo3Ia8bEM
        X0oh3ZcNlCsmA2vAr8PBG4Q/ThvCG/xsWCuMTz/gKfjIn/twGl58xzH22bZsLSQN
        cHZuZalJC4qP71UCTdpnTh9N2Bmv9v05yZEqvd452NE2l0m5AlNLlGzbBn+mekZX
        5y47R6quaTdIpHNjrvw5AgMBAAEwDQYJKoZIhvcNAQELBQADggEBAK9mzSMZfzCs
        ZPRXd1WF+q+OKebmhJma64QjgRzuYqCs6WI7kUqTF2k2l3o5v8e2cnJKIbig89cD
        L7SmttBtHqdcHjKoMDujuqhCsrHntcLYYKc/cgrpQbUC8cL2eelSX0CTS4Ss2VlZ
        saNFwvJ0Yx8P0eDIQkJ3fP57nfe6vrgAQOdU/iqhfvCqhn3RPKVXbuQTdxdBBC0X
        8lVwa+gpSPjphOuoQvavQdi7yXB/V0ZR2a9ifEK2trrKpuMeZSaOMTbzWR3dsdCP
        aiHDurt8SBR77mTNf0NEmeTELe6NYzOshrYV/mwLgOvzCS7UCLb7PmfgiIk3DTdc
        9e3xcRutBgI=
        -----END CERTIFICATE-----
      nsx-t-host: nsxmanager.pks.vmware.local
      nsx-t-insecure: true
      nsx-t-password: Admin!23Admin
      nsx-t-user: admin
  - name: pks-nsx-t-floating-ip-association
    release: pks-nsx-t
    properties:
      cluster-name: 
      floating-ip: 192.168.150.104
      floating-ip-pool-id: d0ece6ff-b7bb-4a55-bc22-f6ec0b7ca297
      master-ip: 
      nsx-t-ca-cert: |-
        -----BEGIN CERTIFICATE-----
        MIIDZDCCAkygAwIBAgIGAWP3qchFMA0GCSqGSIb3DQEBCwUAMHMxJDAiBgNVBAMM
        G25zeG1hbmFnZXIucGtzLnZtd2FyZS5sb2NhbDEPMA0GA1UECgwGVk13YXJlMQww
        CgYDVQQLDANDTkExCzAJBgNVBAYTAlVTMQswCQYDVQQIDAJDQTESMBAGA1UEBwwJ
        UGFsbyBBbHRvMB4XDTE4MDYxMzA1NDEyOVoXDTIzMDYxMjA1NDEyOVowczEkMCIG
        A1UEAwwbbnN4bWFuYWdlci5wa3Mudm13YXJlLmxvY2FsMQ8wDQYDVQQKDAZWTXdh
        cmUxDDAKBgNVBAsMA0NOQTELMAkGA1UEBhMCVVMxCzAJBgNVBAgMAkNBMRIwEAYD
        VQQHDAlQYWxvIEFsdG8wggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDZ
        XSVftNvRA2/jQP/UL1ACKb6qR5TDNTE83ehvoZdRZUMra+R89YaS0y0jfaLk4QT0
        jDGU/BPs6iR6HyivWwkwm8SGBxetyPkrR84UFKX9fJideRAU1TaYIc+NEn53hQjC
        e4YR0Be5+U+yT+N8j/J8kirFydKpIk7YHSDIi3Kpa96NeHb12MhzvmEDo3Ia8bEM
        X0oh3ZcNlCsmA2vAr8PBG4Q/ThvCG/xsWCuMTz/gKfjIn/twGl58xzH22bZsLSQN
        cHZuZalJC4qP71UCTdpnTh9N2Bmv9v05yZEqvd452NE2l0m5AlNLlGzbBn+mekZX
        5y47R6quaTdIpHNjrvw5AgMBAAEwDQYJKoZIhvcNAQELBQADggEBAK9mzSMZfzCs
        ZPRXd1WF+q+OKebmhJma64QjgRzuYqCs6WI7kUqTF2k2l3o5v8e2cnJKIbig89cD
        L7SmttBtHqdcHjKoMDujuqhCsrHntcLYYKc/cgrpQbUC8cL2eelSX0CTS4Ss2VlZ
        saNFwvJ0Yx8P0eDIQkJ3fP57nfe6vrgAQOdU/iqhfvCqhn3RPKVXbuQTdxdBBC0X
        8lVwa+gpSPjphOuoQvavQdi7yXB/V0ZR2a9ifEK2trrKpuMeZSaOMTbzWR3dsdCP
        aiHDurt8SBR77mTNf0NEmeTELe6NYzOshrYV/mwLgOvzCS7UCLb7PmfgiIk3DTdc
        9e3xcRutBgI=
        -----END CERTIFICATE-----
      nsx-t-host: nsxmanager.pks.vmware.local
      nsx-t-insecure: true
      nsx-t-password: Admin!23Admin
      nsx-t-user: admin
      release-floating-ip: false
      t0-router-id: 1748c98f-aeda-416f-b3bb-a60d1b37f441
  vm_type: medium
  stemcell: trusty
  persistent_disk_type: '10240'
  azs:
  - az-1
  networks:
  - name: pks-1ee08f0f-2e8a-45f9-a1f8-5e0d608225b4-cluster-switch
- name: worker
  instances: 2
  jobs:
  - name: docker
    release: docker
    properties:
      bip: 172.17.0.1/24
      default_ulimits:
      - nofile=65536
      env: {}
      flannel: false
      ip_masq: false
      iptables: false
      log_level: error
      log_options:
      - max-size=128m
      - max-file=2
      storage_driver: overlay
      store_dir: "/var/vcap/store"
      tls_cacert: "((tls-docker.ca))"
      tls_cert: "((tls-docker.certificate))"
      tls_key: "((tls-docker.private_key))"
  - name: kubernetes-dependencies
    release: kubo
  - name: kubelet
    release: kubo
    consumes:
      cloud-provider:
        from: worker-cloud-provider
    properties:
      api-token: "((kubelet-password))"
      drain-api-token: "((kubelet-drain-password))"
      tls:
        kubelet: "((tls-kubelet))"
        kubernetes: "((tls-kubernetes))"
  - name: kube-proxy
    release: kubo
    properties:
      api-token: "((kube-proxy-password))"
      tls:
        kubernetes: "((tls-kubernetes))"
  - name: drain-cluster
    release: pks-helpers
  - name: cloud-provider
    release: kubo
    provides:
      cloud-provider:
        as: worker-cloud-provider
    properties:
      cloud-provider:
        type: vsphere
        vsphere:
          datacenter: kubo-dc
          datastore: iscsi-ds-0
          insecure-flag: 1
          password: Admin!23
          server: 192.168.111.24
          user: administrator@vsphere.local
          vms: pcf_vms
          working-dir: "/kubo-dc/vm/pcf_vms/aca565a2-93be-4dc2-85dd-d7a512cc0dd7"
  - name: syslog_forwarder
    release: syslog-migration
    properties:
      syslog:
        address: ''
        ca_cert: 
        migration:
          disabled: false
        permitted_peer: ''
        port: '514'
        tls_enabled: false
        transport: tcp
  - name: nsx-pod-networking
    release: pks-nsx-t
  - name: ncp
    release: pks-nsx-t
    properties:
      authorization-mode: rbac
      nsx-t-ca-cert: |-
        -----BEGIN CERTIFICATE-----
        MIIDZDCCAkygAwIBAgIGAWP3qchFMA0GCSqGSIb3DQEBCwUAMHMxJDAiBgNVBAMM
        G25zeG1hbmFnZXIucGtzLnZtd2FyZS5sb2NhbDEPMA0GA1UECgwGVk13YXJlMQww
        CgYDVQQLDANDTkExCzAJBgNVBAYTAlVTMQswCQYDVQQIDAJDQTESMBAGA1UEBwwJ
        UGFsbyBBbHRvMB4XDTE4MDYxMzA1NDEyOVoXDTIzMDYxMjA1NDEyOVowczEkMCIG
        A1UEAwwbbnN4bWFuYWdlci5wa3Mudm13YXJlLmxvY2FsMQ8wDQYDVQQKDAZWTXdh
        cmUxDDAKBgNVBAsMA0NOQTELMAkGA1UEBhMCVVMxCzAJBgNVBAgMAkNBMRIwEAYD
        VQQHDAlQYWxvIEFsdG8wggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDZ
        XSVftNvRA2/jQP/UL1ACKb6qR5TDNTE83ehvoZdRZUMra+R89YaS0y0jfaLk4QT0
        jDGU/BPs6iR6HyivWwkwm8SGBxetyPkrR84UFKX9fJideRAU1TaYIc+NEn53hQjC
        e4YR0Be5+U+yT+N8j/J8kirFydKpIk7YHSDIi3Kpa96NeHb12MhzvmEDo3Ia8bEM
        X0oh3ZcNlCsmA2vAr8PBG4Q/ThvCG/xsWCuMTz/gKfjIn/twGl58xzH22bZsLSQN
        cHZuZalJC4qP71UCTdpnTh9N2Bmv9v05yZEqvd452NE2l0m5AlNLlGzbBn+mekZX
        5y47R6quaTdIpHNjrvw5AgMBAAEwDQYJKoZIhvcNAQELBQADggEBAK9mzSMZfzCs
        ZPRXd1WF+q+OKebmhJma64QjgRzuYqCs6WI7kUqTF2k2l3o5v8e2cnJKIbig89cD
        L7SmttBtHqdcHjKoMDujuqhCsrHntcLYYKc/cgrpQbUC8cL2eelSX0CTS4Ss2VlZ
        saNFwvJ0Yx8P0eDIQkJ3fP57nfe6vrgAQOdU/iqhfvCqhn3RPKVXbuQTdxdBBC0X
        8lVwa+gpSPjphOuoQvavQdi7yXB/V0ZR2a9ifEK2trrKpuMeZSaOMTbzWR3dsdCP
        aiHDurt8SBR77mTNf0NEmeTELe6NYzOshrYV/mwLgOvzCS7UCLb7PmfgiIk3DTdc
        9e3xcRutBgI=
        -----END CERTIFICATE-----
      nsx-t-host: nsxmanager.pks.vmware.local
      nsx-t-insecure: true
      nsx-t-password: Admin!23Admin
      nsx-t-user: admin
      use-native-loadbalancer: true
  vm_type: medium
  stemcell: trusty
  persistent_disk_type: '10240'
  azs:
  - az-1
  networks:
  - name: pks-1ee08f0f-2e8a-45f9-a1f8-5e0d608225b4-cluster-switch
update:
  canaries: 1
  canary_watch_time: 10000-300000
  update_watch_time: 10000-300000
  max_in_flight: 1
  serial: true
properties:
  kubernetes-api-url: https://192.168.150.104:8443
  nsxt_network: true
variables:
- name: kubelet-password
  type: password
- name: kubelet-drain-password
  type: password
- name: kube-proxy-password
  type: password
- name: kube-controller-manager-password
  type: password
- name: kube-scheduler-password
  type: password
- name: route-sync-password
  type: password
- name: kubo_ca
  type: certificate
  options:
    common_name: ca
    is_ca: true
- name: tls-kubelet
  type: certificate
  options:
    alternative_names: []
    ca: kubo_ca
    common_name: kubelet.cfcr.internal
    organization: system:nodes
- name: tls-kubernetes
  type: certificate
  options:
    alternative_names:
    - 10.100.200.1
    - kubernetes
    - kubernetes.default
    - kubernetes.default.svc
    - kubernetes.default.svc.cluster.local
    - master.cfcr.internal
    - 192.168.150.104
    ca: "/p-bosh/pivotal-container-service-37f4102408dc7e3b4fcf/kubo_odb_ca"
    common_name: 192.168.150.104
    organization: system:masters
- name: service-account-key
  type: rsa
- name: tls-docker
  type: certificate
  options:
    ca: kubo_ca
    common_name: docker.cfcr.internal
- name: tls-etcd
  type: certificate
  options:
    alternative_names:
    - master.cfcr.internal
    ca: kubo_ca
    common_name: master.cfcr.internal
    extended_key_usage:
    - client_auth
    - server_auth
- name: tls-etcdctl
  type: certificate
  options:
    ca: kubo_ca
    common_name: etcdClient
    extended_key_usage:
    - client_auth
- name: tls-heapster
  type: certificate
  options:
    alternative_names:
    - heapster.kube-system.svc.cluster.local
    ca: kubo_ca
    common_name: heapster
- name: tls-influxdb
  type: certificate
  options:
    alternative_names: []
    ca: kubo_ca
    common_name: monitoring-influxdb
- name: kubernetes-dashboard-ca
  type: certificate
  options:
    common_name: ca
    is_ca: true
- name: tls-kubernetes-dashboard
  type: certificate
  options:
    alternative_names: []
    ca: kubernetes-dashboard-ca
    common_name: kubernetesdashboard.cfcr.internal
features:
  use_dns_addresses: true

Succeeded
```

<a href="https://www.dennyzhang.com"><img align="right" width="201" height="268" src="https://raw.githubusercontent.com/USDevOps/mywechat-slack-group/master/images/denny_201706.png"></a>

<a href="https://www.dennyzhang.com"><img align="right" src="https://raw.githubusercontent.com/USDevOps/mywechat-slack-group/master/images/dns_small.png"></a>
# License
- Code is licensed under [MIT License](https://www.dennyzhang.com/wp-content/mit_license.txt).