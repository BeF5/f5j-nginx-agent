補足情報
####

Tips1. curlによるNGINX Agent RESTの結果
====

参考にNGINX Agentの情報をRESTで取得したサンプルを示します

/metrics
----

.. code-block:: cmdin

  curl -s http://10.1.1.5:8081/metrics/

.. code-block:: bash
  :caption: 実行結果サンプル
  :linenos:

  # HELP go_gc_duration_seconds A summary of the pause duration of garbage collection cycles.
  # TYPE go_gc_duration_seconds summary
  go_gc_duration_seconds{quantile="0"} 2.1421e-05
  go_gc_duration_seconds{quantile="0.25"} 0.000119152
  go_gc_duration_seconds{quantile="0.5"} 0.000151643
  go_gc_duration_seconds{quantile="0.75"} 0.000165184
  go_gc_duration_seconds{quantile="1"} 0.00380504
  go_gc_duration_seconds_sum 0.006825104
  go_gc_duration_seconds_count 22
  # HELP go_goroutines Number of goroutines that currently exist.
  # TYPE go_goroutines gauge
  go_goroutines 100
  # HELP go_info Information about the Go environment.
  # TYPE go_info gauge
  go_info{version="go1.19.6"} 1
  # HELP go_memstats_alloc_bytes Number of bytes allocated and still in use.
  # TYPE go_memstats_alloc_bytes gauge
  go_memstats_alloc_bytes 3.271896e+06
  # HELP go_memstats_alloc_bytes_total Total number of bytes allocated, even if freed.
  # TYPE go_memstats_alloc_bytes_total counter
  go_memstats_alloc_bytes_total 6.613096e+07
  # HELP go_memstats_buck_hash_sys_bytes Number of bytes used by the profiling bucket hash table.
  # TYPE go_memstats_buck_hash_sys_bytes gauge
  go_memstats_buck_hash_sys_bytes 5107
  # HELP go_memstats_frees_total Total number of frees.
  # TYPE go_memstats_frees_total counter
  go_memstats_frees_total 358805
  # HELP go_memstats_gc_sys_bytes Number of bytes used for garbage collection system metadata.
  # TYPE go_memstats_gc_sys_bytes gauge
  go_memstats_gc_sys_bytes 9.45484e+06
  # HELP go_memstats_heap_alloc_bytes Number of heap bytes allocated and still in use.
  # TYPE go_memstats_heap_alloc_bytes gauge
  go_memstats_heap_alloc_bytes 3.271896e+06
  # HELP go_memstats_heap_idle_bytes Number of heap bytes waiting to be used.
  # TYPE go_memstats_heap_idle_bytes gauge
  go_memstats_heap_idle_bytes 6.463488e+06
  # HELP go_memstats_heap_inuse_bytes Number of heap bytes that are in use.
  # TYPE go_memstats_heap_inuse_bytes gauge
  go_memstats_heap_inuse_bytes 5.20192e+06
  # HELP go_memstats_heap_objects Number of allocated objects.
  # TYPE go_memstats_heap_objects gauge
  go_memstats_heap_objects 9163
  # HELP go_memstats_heap_released_bytes Number of heap bytes released to OS.
  # TYPE go_memstats_heap_released_bytes gauge
  go_memstats_heap_released_bytes 3.97312e+06
  # HELP go_memstats_heap_sys_bytes Number of heap bytes obtained from system.
  # TYPE go_memstats_heap_sys_bytes gauge
  go_memstats_heap_sys_bytes 1.1665408e+07
  # HELP go_memstats_last_gc_time_seconds Number of seconds since 1970 of last garbage collection.
  # TYPE go_memstats_last_gc_time_seconds gauge
  go_memstats_last_gc_time_seconds 1.6778511732721324e+09
  # HELP go_memstats_lookups_total Total number of pointer lookups.
  # TYPE go_memstats_lookups_total counter
  go_memstats_lookups_total 0
  # HELP go_memstats_mallocs_total Total number of mallocs.
  # TYPE go_memstats_mallocs_total counter
  go_memstats_mallocs_total 367968
  # HELP go_memstats_mcache_inuse_bytes Number of bytes in use by mcache structures.
  # TYPE go_memstats_mcache_inuse_bytes gauge
  go_memstats_mcache_inuse_bytes 2400
  # HELP go_memstats_mcache_sys_bytes Number of bytes used for mcache structures obtained from system.
  # TYPE go_memstats_mcache_sys_bytes gauge
  go_memstats_mcache_sys_bytes 15600
  # HELP go_memstats_mspan_inuse_bytes Number of bytes in use by mspan structures.
  # TYPE go_memstats_mspan_inuse_bytes gauge
  go_memstats_mspan_inuse_bytes 80640
  # HELP go_memstats_mspan_sys_bytes Number of bytes used for mspan structures obtained from system.
  # TYPE go_memstats_mspan_sys_bytes gauge
  go_memstats_mspan_sys_bytes 162720
  # HELP go_memstats_next_gc_bytes Number of heap bytes when next garbage collection will take place.
  # TYPE go_memstats_next_gc_bytes gauge
  go_memstats_next_gc_bytes 6.68908e+06
  # HELP go_memstats_other_sys_bytes Number of bytes used for other system allocations.
  # TYPE go_memstats_other_sys_bytes gauge
  go_memstats_other_sys_bytes 567957
  # HELP go_memstats_stack_inuse_bytes Number of bytes in use by the stack allocator.
  # TYPE go_memstats_stack_inuse_bytes gauge
  go_memstats_stack_inuse_bytes 917504
  # HELP go_memstats_stack_sys_bytes Number of bytes obtained from system for stack allocator.
  # TYPE go_memstats_stack_sys_bytes gauge
  go_memstats_stack_sys_bytes 917504
  # HELP go_memstats_sys_bytes Number of bytes obtained from system.
  # TYPE go_memstats_sys_bytes gauge
  go_memstats_sys_bytes 2.2789136e+07
  # HELP go_threads Number of OS threads created.
  # TYPE go_threads gauge
  go_threads 8
  # HELP process_cpu_seconds_total Total user and system CPU time spent in seconds.
  # TYPE process_cpu_seconds_total counter
  process_cpu_seconds_total 7.46
  # HELP process_max_fds Maximum number of open file descriptors.
  # TYPE process_max_fds gauge
  process_max_fds 524288
  # HELP process_open_fds Number of open file descriptors.
  # TYPE process_open_fds gauge
  process_open_fds 19
  # HELP process_resident_memory_bytes Resident memory size in bytes.
  # TYPE process_resident_memory_bytes gauge
  process_resident_memory_bytes 2.502656e+07
  # HELP process_start_time_seconds Start time of the process since unix epoch in seconds.
  # TYPE process_start_time_seconds gauge
  process_start_time_seconds 1.677851166e+09
  # HELP process_virtual_memory_bytes Virtual memory size in bytes.
  # TYPE process_virtual_memory_bytes gauge
  process_virtual_memory_bytes 7.46848256e+08
  # HELP process_virtual_memory_max_bytes Maximum amount of virtual memory available in bytes.
  # TYPE process_virtual_memory_max_bytes gauge
  process_virtual_memory_max_bytes 1.8446744073709552e+19
  

/nginx
----

.. code-block:: cmdin

  curl -s http://10.1.1.5:8081/nginx/ | jq .

.. code-block:: bash
  :caption: 実行結果サンプル
  :linenos:

  [
    {
      "nginx_id": "b636d4376dea15405589692d3c5d3869ff3a9b26b0e7bb4bb1aa7e658ace1437",
      "version": "1.23.2",
      "conf_path": "/etc/nginx/nginx.conf",
      "process_id": "898",
      "process_path": "/usr/sbin/nginx",
      "start_time": 1677841975000,
      "built_from_source": false,
      "loadable_modules": [
        "ngx_http_app_protect_dos_module-debug",
        "ngx_http_app_protect_dos_module",
        "ngx_http_app_protect_module-debug",
        "ngx_http_app_protect_module",
        "ngx_http_js_module-debug",
        "ngx_http_js_module",
        "ngx_stream_js_module-debug",
        "ngx_stream_js_module"
      ],
      "runtime_modules": [
        "http_addition_module",
        "http_auth_request_module",
        "http_dav_module",
        "http_flv_module",
        "http_gunzip_module",
        "http_gzip_static_module",
        "http_mp4_module",
        "http_random_index_module",
        "http_realip_module",
        "http_secure_link_module",
        "http_slice_module",
        "http_ssl_module",
        "http_stub_status_module",
        "http_sub_module",
        "http_v2_module",
        "mail_ssl_module",
        "stream_realip_module",
        "stream_ssl_module",
        "stream_ssl_preread_module",
        "http_auth_jwt_module",
        "http_f4f_module",
        "http_hls_module",
        "http_session_log_module",
        "http_proxy_protocol_vendor_module",
        "stream_proxy_protocol_vendor_module"
      ],
      "plus": {
        "enabled": true,
        "release": "nginx-plus-r28"
      },
      "ssl": {
        "ssl_type": 0,
        "details": [
          "OpenSSL",
          "1.1.1f",
          "31 Mar 2020"
        ]
      },
      "status_url": "http://localhost:8080/api",
      "configure_args": [
        "",
        "prefix=/etc/nginx",
        "sbin-path=/usr/sbin/nginx",
        "modules-path=/usr/lib/nginx/modules",
        "conf-path=/etc/nginx/nginx.conf",
        "error-log-path=/var/log/nginx/error.log",
        "http-log-path=/var/log/nginx/access.log",
        "pid-path=/var/run/nginx.pid",
        "lock-path=/var/run/nginx.lock",
        "http-client-body-temp-path=/var/cache/nginx/client_temp",
        "http-proxy-temp-path=/var/cache/nginx/proxy_temp",
        "http-fastcgi-temp-path=/var/cache/nginx/fastcgi_temp",
        "http-uwsgi-temp-path=/var/cache/nginx/uwsgi_temp",
        "http-scgi-temp-path=/var/cache/nginx/scgi_temp",
        "user=nginx",
        "group=nginx",
        "with-compat",
        "with-file-aio",
        "with-threads",
        "with-http_addition_module",
        "with-http_auth_request_module",
        "with-http_dav_module",
        "with-http_flv_module",
        "with-http_gunzip_module",
        "with-http_gzip_static_module",
        "with-http_mp4_module",
        "with-http_random_index_module",
        "with-http_realip_module",
        "with-http_secure_link_module",
        "with-http_slice_module",
        "with-http_ssl_module",
        "with-http_stub_status_module",
        "with-http_sub_module",
        "with-http_v2_module",
        "with-mail",
        "with-mail_ssl_module",
        "with-stream",
        "with-stream_realip_module",
        "with-stream_ssl_module",
        "with-stream_ssl_preread_module",
        "build=nginx-plus-r28",
        "with-http_auth_jwt_module",
        "with-http_f4f_module",
        "with-http_hls_module",
        "with-http_session_log_module",
        "with-http_proxy_protocol_vendor_module",
        "with-stream_proxy_protocol_vendor_module",
        "with-cc-opt='-g -O2 -fdebug-prefix-map=/data/builder/debuild/nginx-plus-1.23.2/debian/debuild-base/nginx-plus-1.23.2=. -fstack-protector-strong -Wformat -Werror=format-security -Wp,-D_FORTIFY_SOURCE=2 -fPIC'",
        "with-ld-opt='-Wl,-Bsymbolic-functions -Wl,-z,relro -Wl,-z,now -Wl,--as-needed -pie'"
      ]
    }
  ]

Tips2. curlによるモックアプリケーションの結果
====

/registered
----

.. code-block:: cmdin

  curl -s http://10.1.1.5:54790/registered/ | jq .

.. code-block:: bash
  :caption: 実行結果サンプル
  :linenos:

  {
    "meta": {
      "version": "v2.23.1",
      "display_name": "ip-10-1-1-7",
      "tag": null,
      "instance_group": "",
      "updated": {
        "seconds": 1677820999,
        "nanos": 203935155
      },
      "system_uid": "b437d630-5171-3284-b7b6-0c8087f7ee5e",
      "agent_details": {
        "features": [
          "features_registration",
          "features_nginx-config",
          "features_nginx-ssl-config",
          "features_nginx-counting",
          "features_nginx-config-async",
          "features_metrics",
          "features_metrics-throttle",
          "features_dataplane-status",
          "features_process-watcher",
          "features_file-watcher",
          "features_activity-events",
          "features_agent-api"
        ],
        "extensions": null,
        "tags": null,
        "alias": ""
      }
    },
    "details": [
      {
        "nginx_id": "b636d4376dea15405589692d3c5d3869ff3a9b26b0e7bb4bb1aa7e658ace1437",
        "version": "1.23.2",
        "conf_path": "/etc/nginx/nginx.conf",
        "process_id": "898",
        "process_path": "/usr/sbin/nginx",
        "start_time": 1677841975000,
        "built_from_source": false,
        "loadable_modules": [
          "ngx_http_app_protect_dos_module-debug",
          "ngx_http_app_protect_dos_module",
          "ngx_http_app_protect_module-debug",
          "ngx_http_app_protect_module",
          "ngx_http_js_module-debug",
          "ngx_http_js_module",
          "ngx_stream_js_module-debug",
          "ngx_stream_js_module"
        ],
        "runtime_modules": [
          "http_addition_module",
          "http_auth_request_module",
          "http_dav_module",
          "http_flv_module",
          "http_gunzip_module",
          "http_gzip_static_module",
          "http_mp4_module",
          "http_random_index_module",
          "http_realip_module",
          "http_secure_link_module",
          "http_slice_module",
          "http_ssl_module",
          "http_stub_status_module",
          "http_sub_module",
          "http_v2_module",
          "mail_ssl_module",
          "stream_realip_module",
          "stream_ssl_module",
          "stream_ssl_preread_module",
          "http_auth_jwt_module",
          "http_f4f_module",
          "http_hls_module",
          "http_session_log_module",
          "http_proxy_protocol_vendor_module",
          "stream_proxy_protocol_vendor_module"
        ],
        "plus": {
          "enabled": true,
          "release": "nginx-plus-r28"
        },
        "ssl": {
          "ssl_type": 0,
          "details": [
            "OpenSSL",
            "1.1.1f",
            "31 Mar 2020"
          ]
        },
        "status_url": "http://localhost:8080/api",
        "configure_args": [
          "",
          "prefix=/etc/nginx",
          "sbin-path=/usr/sbin/nginx",
          "modules-path=/usr/lib/nginx/modules",
          "conf-path=/etc/nginx/nginx.conf",
          "error-log-path=/var/log/nginx/error.log",
          "http-log-path=/var/log/nginx/access.log",
          "pid-path=/var/run/nginx.pid",
          "lock-path=/var/run/nginx.lock",
          "http-client-body-temp-path=/var/cache/nginx/client_temp",
          "http-proxy-temp-path=/var/cache/nginx/proxy_temp",
          "http-fastcgi-temp-path=/var/cache/nginx/fastcgi_temp",
          "http-uwsgi-temp-path=/var/cache/nginx/uwsgi_temp",
          "http-scgi-temp-path=/var/cache/nginx/scgi_temp",
          "user=nginx",
          "group=nginx",
          "with-compat",
          "with-file-aio",
          "with-threads",
          "with-http_addition_module",
          "with-http_auth_request_module",
          "with-http_dav_module",
          "with-http_flv_module",
          "with-http_gunzip_module",
          "with-http_gzip_static_module",
          "with-http_mp4_module",
          "with-http_random_index_module",
          "with-http_realip_module",
          "with-http_secure_link_module",
          "with-http_slice_module",
          "with-http_ssl_module",
          "with-http_stub_status_module",
          "with-http_sub_module",
          "with-http_v2_module",
          "with-mail",
          "with-mail_ssl_module",
          "with-stream",
          "with-stream_realip_module",
          "with-stream_ssl_module",
          "with-stream_ssl_preread_module",
          "build=nginx-plus-r28",
          "with-http_auth_jwt_module",
          "with-http_f4f_module",
          "with-http_hls_module",
          "with-http_session_log_module",
          "with-http_proxy_protocol_vendor_module",
          "with-stream_proxy_protocol_vendor_module",
          "with-cc-opt='-g -O2 -fdebug-prefix-map=/data/builder/debuild/nginx-plus-1.23.2/debian/debuild-base/nginx-plus-1.23.2=. -fstack-protector-strong -Wformat -Werror=format-security -Wp,-D_FORTIFY_SOURCE=2 -fPIC'",
          "with-ld-opt='-Wl,-Bsymbolic-functions -Wl,-z,relro -Wl,-z,now -Wl,--as-needed -pie'"
        ]
      }
    ],
    "host": {
      "agent": "v2.23.1",
      "boot": 1677841813,
      "hostname": "ip-10-1-1-7",
      "display_name": "ip-10-1-1-7",
      "os-type": "linux",
      "uuid": "b437d630-5171-3284-b7b6-0c8087f7ee5e",
      "uname": "x86_64",
      "disk_partitions": [
        {
          "mountpoint": "/",
          "device": "/dev/nvme0n1p1",
          "fstype": "ext4"
        },
        {
          "mountpoint": "/snap/lxd/24061",
          "device": "/dev/loop6",
          "fstype": "squashfs"
        },
        {
          "mountpoint": "/snap/snapd/18357",
          "device": "/dev/loop7",
          "fstype": "squashfs"
        },
        {
          "mountpoint": "/snap/amazon-ssm-agent/6312",
          "device": "/dev/loop0",
          "fstype": "squashfs"
        },
        {
          "mountpoint": "/snap/core20/1778",
          "device": "/dev/loop1",
          "fstype": "squashfs"
        },
        {
          "mountpoint": "/snap/core20/1822",
          "device": "/dev/loop5",
          "fstype": "squashfs"
        },
        {
          "mountpoint": "/snap/amazon-ssm-agent/5656",
          "device": "/dev/loop3",
          "fstype": "squashfs"
        },
        {
          "mountpoint": "/snap/snapd/17950",
          "device": "/dev/loop9",
          "fstype": "squashfs"
        },
        {
          "mountpoint": "/snap/core18/2667",
          "device": "/dev/loop2",
          "fstype": "squashfs"
        },
        {
          "mountpoint": "/snap/lxd/22753",
          "device": "/dev/loop8",
          "fstype": "squashfs"
        },
        {
          "mountpoint": "/snap/core18/2697",
          "device": "/dev/loop4",
          "fstype": "squashfs"
        }
      ],
      "network": {
        "interfaces": [
          {
            "mac": "",
            "ipv6": [
              {
                "prefixlen": 128,
                "netmask": "ffff:ffff:ffff:ffff:ffff:ffff:ffff:ffff",
                "address": "::1"
              }
            ],
            "ipv4": [
              {
                "prefixlen": 8,
                "netmask": "255.0.0.0",
                "address": "127.0.0.1"
              }
            ],
            "name": "lo"
          },
          {
            "mac": "06:f1:3b:30:df:c5",
            "ipv6": [
              {
                "prefixlen": 64,
                "netmask": "ffff:ffff:ffff:ffff::",
                "address": "fe80::4f1:3bff:fe30:dfc5"
              }
            ],
            "ipv4": [
              {
                "prefixlen": 24,
                "netmask": "255.255.255.0",
                "address": "10.1.1.5"
              }
            ],
            "name": "ens5"
          }
        ],
        "default": "lo"
      },
      "processor": [
        {
          "model": "1",
          "cores": 1,
          "architecture": "23",
          "mhz": 2199.99,
          "hypervisor": "",
          "cpus": 2,
          "virtualization": "",
          "cache": {
            "Cacheline bytes:": "64",
            "Features:": "ADX,AESNI,AVX,AVX2,AVXSLOW,BMI1,BMI2,CLMUL,CLZERO,CMOV,CMPXCHG8,CX16,F16C,FMA3,FXSR,FXSROPT,HTT,HYPERVISOR,LAHF,LZCNT,MMX,MMXEXT,MOVBE,NX,OSXSAVE,POPCNT,RDRAND,RDSEED,RDTSCP,SCE,SHA,SSE,SSE2,SSE3,SSE4,SSE42,SSE4A,SSSE3,X87,XGETBV1,XSAVE,XSAVEC,XSAVEOPT",
            "L1d": "32768",
            "L1i": "32768",
            "L2": "524288",
            "L3": "8388608",
            "SIMD 2:": "Streaming SIMD 2 Extensions"
          }
        },
        {
          "model": "1",
          "cores": 1,
          "architecture": "23",
          "mhz": 2199.99,
          "hypervisor": "",
          "cpus": 2,
          "virtualization": "",
          "cache": {
            "Cacheline bytes:": "64",
            "Features:": "ADX,AESNI,AVX,AVX2,AVXSLOW,BMI1,BMI2,CLMUL,CLZERO,CMOV,CMPXCHG8,CX16,F16C,FMA3,FXSR,FXSROPT,HTT,HYPERVISOR,LAHF,LZCNT,MMX,MMXEXT,MOVBE,NX,OSXSAVE,POPCNT,RDRAND,RDSEED,RDTSCP,SCE,SHA,SSE,SSE2,SSE3,SSE4,SSE42,SSE4A,SSSE3,X87,XGETBV1,XSAVE,XSAVEC,XSAVEOPT",
            "L1d": "32768",
            "L1i": "32768",
            "L2": "524288",
            "L3": "8388608",
            "SIMD 2:": "Streaming SIMD 2 Extensions"
          }
        }
      ],
      "release": {
        "codename": "linux",
        "id": "ubuntu",
        "name": "debian",
        "version_id": "20.04",
        "version": "5.15.0-1031-aws"
      },
      "tags": null,
      "agent_accessible_dirs": "/etc/nginx:/usr/local/etc/nginx:/usr/share/nginx/modules:/etc/nms"
    },
    "dataplane_software_details": null
  }


/nginxes
----

.. code-block:: cmdin

  curl -s http://10.1.1.5:54790/nginxes/ | jq .

.. code-block:: bash
  :caption: 実行結果サンプル
  :linenos:

  [
    {
      "nginx_id": "b636d4376dea15405589692d3c5d3869ff3a9b26b0e7bb4bb1aa7e658ace1437",
      "version": "1.23.2",
      "conf_path": "/etc/nginx/nginx.conf",
      "process_id": "898",
      "process_path": "/usr/sbin/nginx",
      "start_time": 1677841975000,
      "built_from_source": false,
      "loadable_modules": [
        "ngx_http_app_protect_dos_module-debug",
        "ngx_http_app_protect_dos_module",
        "ngx_http_app_protect_module-debug",
        "ngx_http_app_protect_module",
        "ngx_http_js_module-debug",
        "ngx_http_js_module",
        "ngx_stream_js_module-debug",
        "ngx_stream_js_module"
      ],
      "runtime_modules": [
        "http_addition_module",
        "http_auth_request_module",
        "http_dav_module",
        "http_flv_module",
        "http_gunzip_module",
        "http_gzip_static_module",
        "http_mp4_module",
        "http_random_index_module",
        "http_realip_module",
        "http_secure_link_module",
        "http_slice_module",
        "http_ssl_module",
        "http_stub_status_module",
        "http_sub_module",
        "http_v2_module",
        "mail_ssl_module",
        "stream_realip_module",
        "stream_ssl_module",
        "stream_ssl_preread_module",
        "http_auth_jwt_module",
        "http_f4f_module",
        "http_hls_module",
        "http_session_log_module",
        "http_proxy_protocol_vendor_module",
        "stream_proxy_protocol_vendor_module"
      ],
      "plus": {
        "enabled": true,
        "release": "nginx-plus-r28"
      },
      "ssl": {
        "ssl_type": 0,
        "details": [
          "OpenSSL",
          "1.1.1f",
          "31 Mar 2020"
        ]
      },
      "status_url": "http://localhost:8080/api",
      "configure_args": [
        "",
        "prefix=/etc/nginx",
        "sbin-path=/usr/sbin/nginx",
        "modules-path=/usr/lib/nginx/modules",
        "conf-path=/etc/nginx/nginx.conf",
        "error-log-path=/var/log/nginx/error.log",
        "http-log-path=/var/log/nginx/access.log",
        "pid-path=/var/run/nginx.pid",
        "lock-path=/var/run/nginx.lock",
        "http-client-body-temp-path=/var/cache/nginx/client_temp",
        "http-proxy-temp-path=/var/cache/nginx/proxy_temp",
        "http-fastcgi-temp-path=/var/cache/nginx/fastcgi_temp",
        "http-uwsgi-temp-path=/var/cache/nginx/uwsgi_temp",
        "http-scgi-temp-path=/var/cache/nginx/scgi_temp",
        "user=nginx",
        "group=nginx",
        "with-compat",
        "with-file-aio",
        "with-threads",
        "with-http_addition_module",
        "with-http_auth_request_module",
        "with-http_dav_module",
        "with-http_flv_module",
        "with-http_gunzip_module",
        "with-http_gzip_static_module",
        "with-http_mp4_module",
        "with-http_random_index_module",
        "with-http_realip_module",
        "with-http_secure_link_module",
        "with-http_slice_module",
        "with-http_ssl_module",
        "with-http_stub_status_module",
        "with-http_sub_module",
        "with-http_v2_module",
        "with-mail",
        "with-mail_ssl_module",
        "with-stream",
        "with-stream_realip_module",
        "with-stream_ssl_module",
        "with-stream_ssl_preread_module",
        "build=nginx-plus-r28",
        "with-http_auth_jwt_module",
        "with-http_f4f_module",
        "with-http_hls_module",
        "with-http_session_log_module",
        "with-http_proxy_protocol_vendor_module",
        "with-stream_proxy_protocol_vendor_module",
        "with-cc-opt='-g -O2 -fdebug-prefix-map=/data/builder/debuild/nginx-plus-1.23.2/debian/debuild-base/nginx-plus-1.23.2=. -fstack-protector-strong -Wformat -Werror=format-security -Wp,-D_FORTIFY_SOURCE=2 -fPIC'",
        "with-ld-opt='-Wl,-Bsymbolic-functions -Wl,-z,relro -Wl,-z,now -Wl,--as-needed -pie'"
      ]
    }
  ]

/configs
----

.. code-block:: cmdin

  curl -s http://10.1.1.5:54790/configs/ | jq .

.. code-block:: bash
  :caption: 実行結果サンプル
  :linenos:

  {
    "action": 4,
    "config_data": {
      "system_id": "b437d630-5171-3284-b7b6-0c8087f7ee5e",
      "nginx_id": "b636d4376dea15405589692d3c5d3869ff3a9b26b0e7bb4bb1aa7e658ace1437",
      "checksum": ""
    },
    "zconfig": {
      "contents": "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",
      "checksum": "48201fa519edcbbaf44a644b67c90bf88962cb37946171dbe7dfbad13563529a",
      "root_directory": "/etc/nginx"
    },
    "zaux": null,
    "access_logs": {
      "access_log": [
        {
          "name": "/var/log/nginx/access.log",
          "format": "$remote_addr - $remote_user [$time_local] \"$request\" $status $body_bytes_sent \"$http_referer\" \"$http_user_agent\" \"$http_x_forwarded_for\"",
          "permissions": "0640",
          "readable": true
        },
        {
          "name": "/var/log/nginx/mng_access.log",
          "format": "",
          "permissions": "0640",
          "readable": true
        }
      ]
    },
    "error_logs": {
      "error_log": [
        {
          "name": "/var/log/nginx/error.log",
          "log_level": "notice",
          "permissions": "0640",
          "readable": true
        }
      ]
    },
    "ssl": {},
    "directory_map": {
      "directories": [
        {
          "name": "/etc/nginx",
          "mtime": {
            "seconds": 1677831484,
            "nanos": 812853396
          },
          "permissions": "0755",
          "size": 4096,
          "files": [
            {
              "name": "nginx.conf",
              "lines": 0,
              "mtime": {
                "seconds": 1676950740,
                "nanos": 207957694
              },
              "permissions": "0644",
              "size": 1262,
              "contents": null
            },
            {
              "name": "mime.types",
              "lines": 0,
              "mtime": {
                "seconds": 1654588800
              },
              "permissions": "0644",
              "size": 5349,
              "contents": null
            }
          ]
        },
        {
          "name": "/etc/nginx/conf.d",
          "mtime": {
            "seconds": 1677842773,
            "nanos": 234144884
          },
          "permissions": "0755",
          "size": 4096,
          "files": [
            {
              "name": "api.conf",
              "lines": 0,
              "mtime": {
                "seconds": 1677842773,
                "nanos": 230144860
              },
              "permissions": "0644",
              "size": 342,
              "contents": null
            },
            {
              "name": "default.conf",
              "lines": 0,
              "mtime": {
                "seconds": 1677563029,
                "nanos": 80501179
              },
              "permissions": "0644",
              "size": 519,
              "contents": null
            }
          ]
        }
      ]
    }
  }

/configs/chunked
----

.. code-block:: cmdin

  curl -s http://10.1.1.5:54790/configs/chunked/ | jq .

.. code-block:: bash
  :caption: 実行結果サンプル
  :linenos:

  [
    {
      "Chunk": {
        "header": {
          "meta": {
            "timestamp": {
              "seconds": 1677844095,
              "nanos": 887579726
            },
            "client_id": "b437d630-5171-3284-b7b6-0c8087f7ee5e",
            "message_id": "844d5473-cd9e-4418-9753-a9afe9e44c68",
            "cloud_account_id": "6198b300-ace9-4c4c-83b2-9f64f113b51d"
          },
          "chunks": 2,
          "checksum": "��}�1o|,�\u0001{\u007f�\rl�;B����z�u\u0017\\�CoM\u0012",
          "chunk_size": 4096
        }
      }
    },
    {
      "Chunk": {
        "data": {
          "meta": {
            "timestamp": {
              "seconds": 1677844095,
              "nanos": 887579726
            },
            "client_id": "b437d630-5171-3284-b7b6-0c8087f7ee5e",
            "message_id": "844d5473-cd9e-4418-9753-a9afe9e44c68",
            "cloud_account_id": "6198b300-ace9-4c4c-83b2-9f64f113b51d"
          },
          "chunk_id": 0,
          "data": "eyJhY3Rpb24iOjQsImNvbmZpZ19kYXRhIjp7InN5c3RlbV9pZCI6ImI0MzdkNjMwLTUxNzEtMzI4NC1iN2I2LTBjODA4N2Y3ZWU1ZSIsIm5naW54X2lkIjoiYjYzNmQ0Mzc2ZGVhMTU0MDU1ODk2OTJkM2M1ZDM4NjlmZjNhOWIyNmIwZTdiYjRiYjFhYTdlNjU4YWNlMTQzNyIsImNoZWNrc3VtIjoiIn0sInpjb25maWciOnsiY29udGVudHMiOiJINHNJQUFBQUFBQUEvK3lhWDIvanVCSEE3MW1mWXBBRTJQWUsyWTdqWkxjeDltRngxd0x0UXhHZ1YvU2hhQTJhSE1tMHhUOUxVcmFTUTc1N1FmMnhaWnVLZE50Z3R3dGtnS3h0YVg2YzRaQWNEcVVkbzZOam1YSlpWUCtPcUpMSkQ2OHJrOGxrY2plYmxaK1R5ZVQwYzNwemU5ZDhyNjVmMzF6ZlRYK0F5U3Y3RVpUY09tSittUHpQdGs0Nzk1M0lKU1RLd044K1BjQS9QLzA1eWhSaEM2RlluaUZVSDNZczAyS3hjazR2aU5ZTGJaUkQ2bXFka1ZYejZOREN6K3J2dzF0Z3lnWmErV3RQQytzanFFdlZPb05FbkNqbkZnMUFPY25uMFU2WkRScnZERVZyMFFLUTNLbDVGS0V4eWl3eWxRS010OFNNTTVYV3k2TzhNL0ozcEhLYzRqelNuRUV0cGE3SlpiMklOR2Z6S0lwd2k5SlorRFh5S3JWSnFxUkU2cmlTRnVCNk1wM05vK2NvaW56dmFrVXVhWll6YkZvK0xGREJCWTdjbzBZN0x4VVpKaVRQM01KZkFpQmFaNXdTMy9KWVVZY3Vyc0l3ajBybFRLV0xSQmxCSElBZ1hBSzh1eklvbE1NRlljeEFETTNQTWxEL3VuSmM0Q0pUbEdUL2hvc3JnNTl6dE80QzNrVVFsSGRYMWhHWFc3aGFLdmE0V0Q0NnRBdUwwc0hGVlRsMEJoTTBhRjVvb1ZiMDloY2tSZWt1R3Jid3J1K0lZY2o4dDR0M2RhY0k5Y01YSEs3cVZqbGVaWDlyd3FKa0NjK2E2SUtTVlN3dkhkVUxxWFJ1Vi92cjVZME5vaVlaMytMQ0IwVGxEdUR1dHI1M21UNXgzZEp0UnE0MVpqNmRqdGo0eHpLdlZrTjlDYi84OUREK3g4OFBvSTBxSG9GSUJuNG13NUprUkZJdVUxaG1pbTZpeStpeUdzSjZZbHpDbndvaWRJYmdHK05wYnNyUkxsZk9Mejg5bkRSU3U1anJ1bzE2VVN3SjNhQmsreVlCNEVsSkJOOS9pMmFMeHNMZGJETS8zSzZ1UWcxZWo3QnlZa1NWdUwrZTNzeHVPM1dubmJyUHRYZTFmc3VaakZ1SEVzNGFMaWZYNHNUVmxrSVp5NFVtMXA3MGRHL3g4am42MXRuMi8wL09weXJSL0pXTGdKNzlmM0k3UGR2LzM5L08zdmIvcnlGSEM3QmVleDhtSHliejAveDZrbDZGVEJlSEZMdmZZNnI5Qi93a3F0c3NtOUVjZG9ZNy9OaWsyMnJaTW03OFZyaEZDeGtYM1BuVVZ6VUtUb0ZiSVh4NitFdXAvK3pUWnR2Q1J4akRyOVUxTHdiTDl1RS92eHY5K1BzcjhKdUd2UitQcjFiS3VqRWpkclZVeExEUnlva01OQnBCSkVvM3Ivam5FK2Mvd2lseDZJbFJ5dmxOT2JkbWJGZkVZQjBPcnpadlBQMmU4c3o1K3ErcmlsZk1BVDNyLzNveWVYK3kvbWQzMDdmNi82dklvVHdvRThFaU5TcHZDdEZ5czIzcWhYMU5VR2NNaXpRMzNEM0dUVjF3NzVQR2MzUUpPNUpFNGJSU0o1WFdLUUFsV1dhNHI4TGF0eG9EUHZzTTFZT0w4L2xNYyt1VVdCenEzOUhhS25rQjl0Rm1LcjJ2UFAySUdiR09VNHZFME5YOTdmVnNkcGJUamhMYXdiNVdHYWVQaTdLbzdEWmZhVldtRHltd1ZiVDRsSFUvSHJlSG9Va29QcWhTZGNmMWV0N3Q2VUFMMzNvYXZzazNrdUR4OHBWdHZKei95MHIvdFA2YlR0N3F2NjhpVVRuZ2RjSndXTGl5bEFrZjBNK2wxRjA1QWZaUUFKV05VR3VIdGdIVTJoWlpETGNPUldPVEM1TGlPT1hKVURMbFNadGNhMHdIa3FYcVdxZjdqV2ovMEdWTnRzUlN3N1Y3Q2JmbklIRksvS0d2MzE3cEhEWFc5cEpnZklBUEVSYkVyWVlHV1J5TnFzN0tCMGVEeEJXdVJXNGxHOWxjanRaVGdTT2lkY3l3Q3BVeVorU2FzQk55Ui9Sb044RGwzWkczUlV5VjBNcFgrcjNreXRIbUdVNDVJY2gyOEZ6eXF1MjVwT1hRcVFSYXBtM1NidFArd2F6RWJsUC85OVRHSFUrRyt1eDQ0ditPL040SGVpbDBEKzVWMnVnT2wzM0lIc1hsRVZyRW5LcGhjNHBUZFV5dWgwWjZmUnpuSWhZMjd1K2xsN0tqSlpvbzZjWTdOVGpFNEhYbngrajBONkRUNWhIblNZYUpmWUhLdDlnSnI0bUJIVEdBeEFSeWxCMFFiSzkwamdwQzR5V1hLeXhtazA1MDlia0lrSGFuRE9zeHloUTlKelViRUc3TmtnQ3ByT3ROeHRvQ2FndUVCeEtyRzJEWnVJQmx2NDc4Ynh3SmpXbHVndXRaM09RZndtaXFWSnBoak1TNDFXZ2pzck9Nc0dtU1hBLzVkR1owSTU3Q3BMQXhGaFM3TTArUkJiYXRtdlN6V3kzWFNJT1JSdVU2U2ExMmFMVGk0ZnlzZFFlcGlPVjJwRFJLcG1ndVVMcFJhb2hlY1ZyWEhJb0ZkdWNPVWh1MEtGMTFjQUxGOUdEU2FvT0UyUldpSzIxMlJDaEErdDNwMEUvRnV2cXBVUllpcXc2dE5sWkp3aWtHSFJmWjBjK085eXM5b3JVTHJOMStSMXB4RU5tby9Qd3lCNHJNZnBFRFByblVML0s0VEVVMmF1NThtUnRNMFE0MzZqS0VkcUwrNWptNkkxYjBXdlZLNTJnUnYzOHFxeGlEMW1KSENuMGZXTlcrOXFHS3ZHeVROaHZxTWRuZVpXSVdMQ3JXeExCOStSQ2cxekxUY2ZzMTJ6RXRzOEF5SzJKQk5tZ3hleW54bWp5d014V3h4bkNhYlluT1FBY2pySG1tZWdwRWJTaG90Z3pSaHBpK0FUS2hqYmlJRGJJVmNiRW1kRU5TakFXUkpNWGphdGlFUGJiWU03QUFGa21RWENtNjJaRXR4a2xHNmplZHArUXVPS3pXNVVuQ1g0eVQ1WUZFVnNTTzlsYTBYc1Z0UW5CeE8vbGpURWxNMFhUWlptaEFvd0JxZ3VZTHphVjFKSHZCaVVJSENvRENuMmo3eXZIaWNPdzlZcTFPZWl0NXIzU09saStVKytTSjYwQjEySDdwMzRrdXVRUXNFRmdXOEh0UUN3d0RDMkVZS1FMNzhpQ1NXd1g4aTJsaE9RaXJRZGptUDBPUW5IRTFGcHp4VHVpa0NjNmdWTi9zRjNQVnhQQUhCMExmdEVtVkRqNG1xalJ0azBVc1pyMEpvTFk1SThla1FaS1YzL3RJUStwUWJUbEROYjVKOWRBVFhxbDZrOVladnNLRm52YWZ3U3R4OWhpY0RlUkE2Tmt4K1J0R0JsTVF6U09kQ3YrY2M3cHhYSFNmc3c2NDJyYkpIUzc3dC90S3ZHb2JMZUlrMnc1RGsyeDdUSXJaUUZMTVRzbWh4MmdoMHhQU3hzUU9PUkFUV3dDeHlSbTlFME9jM29sVGoyMzViWURkTFo5L1Y2OWozK1JOM3VSTnZwcjhOd0FBLy85VjE4RGlBQzRBQUE9PSIsImNoZWNrc3VtIjoiNDgyMDFmYTUxOWVkY2JiYWY0NGE2NDRiNjdjOTBiZjg4OTYyY2IzNzk0NjE3MWRiZTdkZmJhZDEzNTYzNTI5YSIsInJvb3RfZGlyZWN0b3J5IjoiL2V0Yy9uZ2lueCJ9LCJ6YXV4IjpudWxsLCJhY2Nlc3NfbG9ncyI6eyJhY2Nlc3NfbG9nIjpbeyJuYW1lIjoiL3Zhci9sb2cvbmdpbngvYWNjZXNzLmxvZyIsImZvcm1hdCI6IiRyZW1vdGVfYWRkciAtICRyZW1vdGVfdXNlciBbJHRpbWVfbG9jYWxdIFwiJHJlcXVlc3RcIiAkc3RhdHVzICRib2R5X2J5dGVzX3NlbnQgXCIkaHR0cF9yZWZlcmVyXCIgXCIkaHR0cF91c2VyX2FnZW50XCIgXCIkaHR0cF94X2ZvcndhcmRlZF9mb3JcIiIsInBlcm1pc3Npb25zIjoiMDY0MCIsInJlYWRhYmxlIjp0cnVlfSx7Im5hbWUiOiIvdmFyL2xvZy9uZ2lueC9tbmdfYWNjZXNzLmxvZyIsImZvcm1hdCI6IiIsInBlcm1pc3Npb25zIjoiMDY0MCIsInJlYWRhYmxlIjp0cnVlfV19LCJlcnJvcl9sb2dzIjp7ImVycm9yX2xvZyI6W3sibmFtZSI6Ii92YXIvbG9nL25naW54L2Vycm9yLmxvZyIsImxvZ19sZXZlbCI6Im5vdGljZSIsInBlcm1pc3Npb25zIjoiMDY0MCIsInJlYWRhYmxlIjp0cnVlfV19LCJzc2wiOnt9LCJkaXJlY3RvcnlfbWFwIjp7ImRpcmVjdG9yaWVzIjpbeyJuYW1lIjoiL2V0Yy9uZ2lueCIsIm10aW1lIjp7InNlY29uZHMiOjE2Nzc4MzE0ODQsIm5hbm9zIjo4MTI4NTMzOTZ9LCJwZXJtaXNzaW9ucyI6IjA3NTUiLCJzaXplIjo0MDk2LCJmaWxlcyI6W3sibmFtZSI6Im5naW54LmNvbmYiLCJsaW5lcyI6MCwibXRpbWUiOnsic2Vjb25kcyI6MTY3Njk1MDc0MCwibmFub3MiOjIwNzk1NzY5NH0sInBlcm1pc3Npb25zIjoiMDY0NCIsInNpemUiOjEyNjIsImNvbnRlbnRzIjpudWxsfSx7Im5hbWUiOiJtaW1lLnR5cGVzIiwibGluZXMiOjAsIm10aW1lIjp7InNlY29uZHMiOjE2NTQ1ODg4MDB9LCJwZXJtaXNzaW9ucyI6IjA2NDQiLCJzaXplIjo1MzQ5LCJjb250ZW50cyI6bnVsbH1dfSx7Im5hbWUiOiIvZXRjL25naW54L2NvbmYuZCIsIm10aW1lIjp7InNlY29uZHMiOjE2Nzc4NDI3NzMsIm5hbm9zIjoyMzQxNDQ4ODR9LCJwZXJtaXNzaW9ucyI6IjA3NTUiLCJzaXplIjo0MDk2LCJmaWxlcyI6W3sibmFtZSI6ImFwaS5jb25mIiwibGluZXMiOjAsIm10aW1lIjp7InNlY29uZA=="
        }
      }
    },
    {
      "Chunk": {
        "data": {
          "meta": {
            "timestamp": {
              "seconds": 1677844095,
              "nanos": 887579726
            },
            "client_id": "b437d630-5171-3284-b7b6-0c8087f7ee5e",
            "message_id": "844d5473-cd9e-4418-9753-a9afe9e44c68",
            "cloud_account_id": "6198b300-ace9-4c4c-83b2-9f64f113b51d"
          },
          "chunk_id": 1,
          "data": "cyI6MTY3Nzg0Mjc3MywibmFub3MiOjIzMDE0NDg2MH0sInBlcm1pc3Npb25zIjoiMDY0NCIsInNpemUiOjM0MiwiY29udGVudHMiOm51bGx9LHsibmFtZSI6ImRlZmF1bHQuY29uZiIsImxpbmVzIjowLCJtdGltZSI6eyJzZWNvbmRzIjoxNjc3NTYzMDI5LCJuYW5vcyI6ODA1MDExNzl9LCJwZXJtaXNzaW9ucyI6IjA2NDQiLCJzaXplIjo1MTksImNvbnRlbnRzIjpudWxsfV19XX19"
        }
      }
    }
  ]

/configs/raw
----

.. code-block:: cmdin

  curl -s http://10.1.1.5:54790/configs/raw/ | jq .

.. code-block:: bash
  :caption: 実行結果サンプル
  :linenos:

  {
    "/etc/nginx/conf.d/api.conf": "server {\n    listen 8080;\n    access_log /var/log/nginx/mng_access.log;\n\n    location /api {\n        api write=on;\n        # directives limiting access to the API\n    }\n\n#    location = / {\n#        rewrite ^(.*)$ https://$host/dashboard.html permanent;\n#    }\n\n    location = /dashboard.html {\n        root   /usr/share/nginx/html;\n    }\n\n}\n",
    "/etc/nginx/conf.d/default.conf": "upstream server_group {\n    zone backend 64k;\n    server security-backend1:80;\n}\n# waf\nserver {\n    listen 80;\n    app_protect_enable on;\n    app_protect_security_log_enable on;\n    app_protect_security_log \"/etc/nginx/conf.d/custom_log_format.json\" syslog:server=elasticsearch:5144;\n\n    location / {\n        app_protect_policy_file \"/etc/nginx/conf.d/custom_policy.json\";\n        proxy_pass http://server_group;\n    }\n}\n# no waf\nserver {\n    listen 81;\n    location / {\n        proxy_pass http://server_group;\n    }\n}",
    "/etc/nginx/mime.types": "\ntypes {\n    text/html                                        html htm shtml;\n    text/css                                         css;\n    text/xml                                         xml;\n    image/gif                                        gif;\n    image/jpeg                                       jpeg jpg;\n    application/javascript                           js;\n    application/atom+xml                             atom;\n    application/rss+xml                              rss;\n\n    text/mathml                                      mml;\n    text/plain                                       txt;\n    text/vnd.sun.j2me.app-descriptor                 jad;\n    text/vnd.wap.wml                                 wml;\n    text/x-component                                 htc;\n\n    image/avif                                       avif;\n    image/png                                        png;\n    image/svg+xml                                    svg svgz;\n    image/tiff                                       tif tiff;\n    image/vnd.wap.wbmp                               wbmp;\n    image/webp                                       webp;\n    image/x-icon                                     ico;\n    image/x-jng                                      jng;\n    image/x-ms-bmp                                   bmp;\n\n    font/woff                                        woff;\n    font/woff2                                       woff2;\n\n    application/java-archive                         jar war ear;\n    application/json                                 json;\n    application/mac-binhex40                         hqx;\n    application/msword                               doc;\n    application/pdf                                  pdf;\n    application/postscript                           ps eps ai;\n    application/rtf                                  rtf;\n    application/vnd.apple.mpegurl                    m3u8;\n    application/vnd.google-earth.kml+xml             kml;\n    application/vnd.google-earth.kmz                 kmz;\n    application/vnd.ms-excel                         xls;\n    application/vnd.ms-fontobject                    eot;\n    application/vnd.ms-powerpoint                    ppt;\n    application/vnd.oasis.opendocument.graphics      odg;\n    application/vnd.oasis.opendocument.presentation  odp;\n    application/vnd.oasis.opendocument.spreadsheet   ods;\n    application/vnd.oasis.opendocument.text          odt;\n    application/vnd.openxmlformats-officedocument.presentationml.presentation\n                                                     pptx;\n    application/vnd.openxmlformats-officedocument.spreadsheetml.sheet\n                                                     xlsx;\n    application/vnd.openxmlformats-officedocument.wordprocessingml.document\n                                                     docx;\n    application/vnd.wap.wmlc                         wmlc;\n    application/wasm                                 wasm;\n    application/x-7z-compressed                      7z;\n    application/x-cocoa                              cco;\n    application/x-java-archive-diff                  jardiff;\n    application/x-java-jnlp-file                     jnlp;\n    application/x-makeself                           run;\n    application/x-perl                               pl pm;\n    application/x-pilot                              prc pdb;\n    application/x-rar-compressed                     rar;\n    application/x-redhat-package-manager             rpm;\n    application/x-sea                                sea;\n    application/x-shockwave-flash                    swf;\n    application/x-stuffit                            sit;\n    application/x-tcl                                tcl tk;\n    application/x-x509-ca-cert                       der pem crt;\n    application/x-xpinstall                          xpi;\n    application/xhtml+xml                            xhtml;\n    application/xspf+xml                             xspf;\n    application/zip                                  zip;\n\n    application/octet-stream                         bin exe dll;\n    application/octet-stream                         deb;\n    application/octet-stream                         dmg;\n    application/octet-stream                         iso img;\n    application/octet-stream                         msi msp msm;\n\n    audio/midi                                       mid midi kar;\n    audio/mpeg                                       mp3;\n    audio/ogg                                        ogg;\n    audio/x-m4a                                      m4a;\n    audio/x-realaudio                                ra;\n\n    video/3gpp                                       3gpp 3gp;\n    video/mp2t                                       ts;\n    video/mp4                                        mp4;\n    video/mpeg                                       mpeg mpg;\n    video/quicktime                                  mov;\n    video/webm                                       webm;\n    video/x-flv                                      flv;\n    video/x-m4v                                      m4v;\n    video/x-mng                                      mng;\n    video/x-ms-asf                                   asx asf;\n    video/x-ms-wmv                                   wmv;\n    video/x-msvideo                                  avi;\n}\n",
    "/etc/nginx/nginx.conf": "# for NAP WAF\nload_module modules/ngx_http_app_protect_module.so;\n# for NAP DoS\nload_module modules/ngx_http_app_protect_dos_module.so;\n# for NJS\nload_module modules/ngx_http_js_module.so;\nload_module modules/ngx_stream_js_module.so;\nuser  nginx;\nworker_processes  auto;\n\nerror_log  /var/log/nginx/error.log notice;\npid        /var/run/nginx.pid;\n\n\nevents {\n    worker_connections  1024;\n}\n\n\nhttp {\n    include       /etc/nginx/mime.types;\n    default_type  application/octet-stream;\n\n    log_format  main  '$remote_addr - $remote_user [$time_local] \"$request\" '\n                      '$status $body_bytes_sent \"$http_referer\" '\n                      '\"$http_user_agent\" \"$http_x_forwarded_for\"';\n\n    access_log  /var/log/nginx/access.log  main;\n\n    sendfile        on;\n    #tcp_nopush     on;\n\n    keepalive_timeout  65;\n\n    #gzip  on;\n\n    include /etc/nginx/conf.d/*.conf;\n}\n\n\n# TCP/UDP proxy and load balancing block\n#\n#stream {\n    # Example configuration for TCP load balancing\n\n    #upstream stream_backend {\n    #    zone tcp_servers 64k;\n    #    server backend1.example.com:12345;\n    #    server backend2.example.com:12345;\n    #}\n\n    #server {\n    #    listen 12345;\n    #    status_zone tcp_server;\n    #    proxy_pass stream_backend;\n    #}\n#}\n"
  }

/metrics
----

.. code-block:: cmdin

  curl -s http://10.1.1.5:54790/metrics/ | jq .

.. code-block:: bash
  :caption: 実行結果サンプル
  :linenos:

  [
    {
      "meta": {
        "timestamp": null,
        "client_id": "",
        "message_id": "",
        "cloud_account_id": ""
      },
      "type": 0,
      "data": [
        {
          "timestamp": {
            "seconds": 1677842843,
            "nanos": 517566302
          },
          "dimensions": [
            {
              "name": "system_id",
              "value": "b437d630-5171-3284-b7b6-0c8087f7ee5e"
            },
            {
              "name": "hostname",
              "value": "ip-10-1-1-7"
            },
            {
              "name": "system.tags",
              "value": ""
            },
            {
              "name": "instance_group",
              "value": ""
            },
            {
              "name": "display_name",
              "value": "ip-10-1-1-7"
            },
            {
              "name": "nginx_id",
              "value": ""
            }
          ],
          ** 省略 **