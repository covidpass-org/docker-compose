# Docker-Compose
This repository contains the docker-compose.yml and all other files to run the covidpass infrastructure

## Prometheus-Metrics
This docker-compose exports the traefik service to the /traefik-metrics endpoint which is secured using basic-auth.
The metrics endpoint doesn't contain any personal informations like ip-address or user-agent.
It only exports general service-health realted information like how many 404 errors and how many total accesses received the service.

Here's a the output of the prometheus metrics endpoint:
<details>
# HELP go_gc_duration_seconds A summary of the pause duration of garbage collection cycles.
# TYPE go_gc_duration_seconds summary
go_gc_duration_seconds{quantile="0"} 2.6767e-05
go_gc_duration_seconds{quantile="0.25"} 6.1459e-05
go_gc_duration_seconds{quantile="0.5"} 0.000202684
go_gc_duration_seconds{quantile="0.75"} 0.001206443
go_gc_duration_seconds{quantile="1"} 0.004975022
go_gc_duration_seconds_sum 0.009420863
go_gc_duration_seconds_count 12
# HELP go_goroutines Number of goroutines that currently exist.
# TYPE go_goroutines gauge
go_goroutines 54
# HELP go_info Information about the Go environment.
# TYPE go_info gauge
go_info{version="go1.16.5"} 1
# HELP go_memstats_alloc_bytes Number of bytes allocated and still in use.
# TYPE go_memstats_alloc_bytes gauge
go_memstats_alloc_bytes 6.027744e+06
# HELP go_memstats_alloc_bytes_total Total number of bytes allocated, even if freed.
# TYPE go_memstats_alloc_bytes_total counter
go_memstats_alloc_bytes_total 4.0965608e+07
# HELP go_memstats_buck_hash_sys_bytes Number of bytes used by the profiling bucket hash table.
# TYPE go_memstats_buck_hash_sys_bytes gauge
go_memstats_buck_hash_sys_bytes 1.458365e+06
# HELP go_memstats_frees_total Total number of frees.
# TYPE go_memstats_frees_total counter
go_memstats_frees_total 184896
# HELP go_memstats_gc_cpu_fraction The fraction of this program's available CPU time used by the GC since the program started.
# TYPE go_memstats_gc_cpu_fraction gauge
go_memstats_gc_cpu_fraction 0.0002185524783981112
# HELP go_memstats_gc_sys_bytes Number of bytes used for garbage collection system metadata.
# TYPE go_memstats_gc_sys_bytes gauge
go_memstats_gc_sys_bytes 5.785008e+06
# HELP go_memstats_heap_alloc_bytes Number of heap bytes allocated and still in use.
# TYPE go_memstats_heap_alloc_bytes gauge
go_memstats_heap_alloc_bytes 6.027744e+06
# HELP go_memstats_heap_idle_bytes Number of heap bytes waiting to be used.
# TYPE go_memstats_heap_idle_bytes gauge
go_memstats_heap_idle_bytes 5.783552e+07
# HELP go_memstats_heap_inuse_bytes Number of heap bytes that are in use.
# TYPE go_memstats_heap_inuse_bytes gauge
go_memstats_heap_inuse_bytes 8.388608e+06
# HELP go_memstats_heap_objects Number of allocated objects.
# TYPE go_memstats_heap_objects gauge
go_memstats_heap_objects 32064
# HELP go_memstats_heap_released_bytes Number of heap bytes released to OS.
# TYPE go_memstats_heap_released_bytes gauge
go_memstats_heap_released_bytes 5.6508416e+07
# HELP go_memstats_heap_sys_bytes Number of heap bytes obtained from system.
# TYPE go_memstats_heap_sys_bytes gauge
go_memstats_heap_sys_bytes 6.6224128e+07
# HELP go_memstats_last_gc_time_seconds Number of seconds since 1970 of last garbage collection.
# TYPE go_memstats_last_gc_time_seconds gauge
go_memstats_last_gc_time_seconds 1.6250489351384335e+09
# HELP go_memstats_lookups_total Total number of pointer lookups.
# TYPE go_memstats_lookups_total counter
go_memstats_lookups_total 0
# HELP go_memstats_mallocs_total Total number of mallocs.
# TYPE go_memstats_mallocs_total counter
go_memstats_mallocs_total 216960
# HELP go_memstats_mcache_inuse_bytes Number of bytes in use by mcache structures.
# TYPE go_memstats_mcache_inuse_bytes gauge
go_memstats_mcache_inuse_bytes 1200
# HELP go_memstats_mcache_sys_bytes Number of bytes used for mcache structures obtained from system.
# TYPE go_memstats_mcache_sys_bytes gauge
go_memstats_mcache_sys_bytes 16384
# HELP go_memstats_mspan_inuse_bytes Number of bytes in use by mspan structures.
# TYPE go_memstats_mspan_inuse_bytes gauge
go_memstats_mspan_inuse_bytes 111112
# HELP go_memstats_mspan_sys_bytes Number of bytes used for mspan structures obtained from system.
# TYPE go_memstats_mspan_sys_bytes gauge
go_memstats_mspan_sys_bytes 163840
# HELP go_memstats_next_gc_bytes Number of heap bytes when next garbage collection will take place.
# TYPE go_memstats_next_gc_bytes gauge
go_memstats_next_gc_bytes 1.1771392e+07
# HELP go_memstats_other_sys_bytes Number of bytes used for other system allocations.
# TYPE go_memstats_other_sys_bytes gauge
go_memstats_other_sys_bytes 523675
# HELP go_memstats_stack_inuse_bytes Number of bytes in use by the stack allocator.
# TYPE go_memstats_stack_inuse_bytes gauge
go_memstats_stack_inuse_bytes 884736
# HELP go_memstats_stack_sys_bytes Number of bytes obtained from system for stack allocator.
# TYPE go_memstats_stack_sys_bytes gauge
go_memstats_stack_sys_bytes 884736
# HELP go_memstats_sys_bytes Number of bytes obtained from system.
# TYPE go_memstats_sys_bytes gauge
go_memstats_sys_bytes 7.5056136e+07
# HELP go_threads Number of OS threads created.
# TYPE go_threads gauge
go_threads 11
# HELP process_cpu_seconds_total Total user and system CPU time spent in seconds.
# TYPE process_cpu_seconds_total counter
process_cpu_seconds_total 2.4
# HELP process_max_fds Maximum number of open file descriptors.
# TYPE process_max_fds gauge
process_max_fds 1.048576e+06
# HELP process_open_fds Number of open file descriptors.
# TYPE process_open_fds gauge
process_open_fds 17
# HELP process_resident_memory_bytes Resident memory size in bytes.
# TYPE process_resident_memory_bytes gauge
process_resident_memory_bytes 5.9674624e+07
# HELP process_start_time_seconds Start time of the process since unix epoch in seconds.
# TYPE process_start_time_seconds gauge
process_start_time_seconds 1.62504854775e+09
# HELP process_virtual_memory_bytes Virtual memory size in bytes.
# TYPE process_virtual_memory_bytes gauge
process_virtual_memory_bytes 8.07022592e+08
# HELP process_virtual_memory_max_bytes Maximum amount of virtual memory available in bytes.
# TYPE process_virtual_memory_max_bytes gauge
process_virtual_memory_max_bytes -1
# HELP traefik_config_last_reload_failure Last config reload failure
# TYPE traefik_config_last_reload_failure gauge
traefik_config_last_reload_failure 0
# HELP traefik_config_last_reload_success Last config reload success
# TYPE traefik_config_last_reload_success gauge
traefik_config_last_reload_success 1.625048553e+09
# HELP traefik_config_reloads_failure_total Config failure reloads
# TYPE traefik_config_reloads_failure_total counter
traefik_config_reloads_failure_total 0
# HELP traefik_config_reloads_total Config reloads
# TYPE traefik_config_reloads_total counter
traefik_config_reloads_total 4
# HELP traefik_entrypoint_open_connections How many open connections exist on an entrypoint, partitioned by method and protocol.
# TYPE traefik_entrypoint_open_connections gauge
traefik_entrypoint_open_connections{entrypoint="websecure",method="GET",protocol="http"} 1
traefik_entrypoint_open_connections{entrypoint="websecure",method="OPTIONS",protocol="http"} 0
traefik_entrypoint_open_connections{entrypoint="websecure",method="POST",protocol="http"} 0
# HELP traefik_entrypoint_request_duration_seconds How long it took to process the request on an entrypoint, partitioned by status code, protocol, and method.
# TYPE traefik_entrypoint_request_duration_seconds histogram
traefik_entrypoint_request_duration_seconds_bucket{code="200",entrypoint="websecure",method="GET",protocol="http",le="0.1"} 33
traefik_entrypoint_request_duration_seconds_bucket{code="200",entrypoint="websecure",method="GET",protocol="http",le="0.3"} 33
traefik_entrypoint_request_duration_seconds_bucket{code="200",entrypoint="websecure",method="GET",protocol="http",le="1.2"} 33
traefik_entrypoint_request_duration_seconds_bucket{code="200",entrypoint="websecure",method="GET",protocol="http",le="5"} 33
traefik_entrypoint_request_duration_seconds_bucket{code="200",entrypoint="websecure",method="GET",protocol="http",le="+Inf"} 33
traefik_entrypoint_request_duration_seconds_sum{code="200",entrypoint="websecure",method="GET",protocol="http"} 0.30760226799999996
traefik_entrypoint_request_duration_seconds_count{code="200",entrypoint="websecure",method="GET",protocol="http"} 33
traefik_entrypoint_request_duration_seconds_bucket{code="200",entrypoint="websecure",method="POST",protocol="http",le="0.1"} 2
traefik_entrypoint_request_duration_seconds_bucket{code="200",entrypoint="websecure",method="POST",protocol="http",le="0.3"} 3
traefik_entrypoint_request_duration_seconds_bucket{code="200",entrypoint="websecure",method="POST",protocol="http",le="1.2"} 3
traefik_entrypoint_request_duration_seconds_bucket{code="200",entrypoint="websecure",method="POST",protocol="http",le="5"} 3
traefik_entrypoint_request_duration_seconds_bucket{code="200",entrypoint="websecure",method="POST",protocol="http",le="+Inf"} 3
traefik_entrypoint_request_duration_seconds_sum{code="200",entrypoint="websecure",method="POST",protocol="http"} 0.24641347
traefik_entrypoint_request_duration_seconds_count{code="200",entrypoint="websecure",method="POST",protocol="http"} 3
traefik_entrypoint_request_duration_seconds_bucket{code="204",entrypoint="websecure",method="OPTIONS",protocol="http",le="0.1"} 3
traefik_entrypoint_request_duration_seconds_bucket{code="204",entrypoint="websecure",method="OPTIONS",protocol="http",le="0.3"} 3
traefik_entrypoint_request_duration_seconds_bucket{code="204",entrypoint="websecure",method="OPTIONS",protocol="http",le="1.2"} 3
traefik_entrypoint_request_duration_seconds_bucket{code="204",entrypoint="websecure",method="OPTIONS",protocol="http",le="5"} 3
traefik_entrypoint_request_duration_seconds_bucket{code="204",entrypoint="websecure",method="OPTIONS",protocol="http",le="+Inf"} 3
traefik_entrypoint_request_duration_seconds_sum{code="204",entrypoint="websecure",method="OPTIONS",protocol="http"} 0.105942341
traefik_entrypoint_request_duration_seconds_count{code="204",entrypoint="websecure",method="OPTIONS",protocol="http"} 3
traefik_entrypoint_request_duration_seconds_bucket{code="304",entrypoint="websecure",method="GET",protocol="http",le="0.1"} 6
traefik_entrypoint_request_duration_seconds_bucket{code="304",entrypoint="websecure",method="GET",protocol="http",le="0.3"} 6
traefik_entrypoint_request_duration_seconds_bucket{code="304",entrypoint="websecure",method="GET",protocol="http",le="1.2"} 6
traefik_entrypoint_request_duration_seconds_bucket{code="304",entrypoint="websecure",method="GET",protocol="http",le="5"} 6
traefik_entrypoint_request_duration_seconds_bucket{code="304",entrypoint="websecure",method="GET",protocol="http",le="+Inf"} 6
traefik_entrypoint_request_duration_seconds_sum{code="304",entrypoint="websecure",method="GET",protocol="http"} 0.056738237000000004
traefik_entrypoint_request_duration_seconds_count{code="304",entrypoint="websecure",method="GET",protocol="http"} 6
traefik_entrypoint_request_duration_seconds_bucket{code="499",entrypoint="websecure",method="GET",protocol="http",le="0.1"} 1
traefik_entrypoint_request_duration_seconds_bucket{code="499",entrypoint="websecure",method="GET",protocol="http",le="0.3"} 1
traefik_entrypoint_request_duration_seconds_bucket{code="499",entrypoint="websecure",method="GET",protocol="http",le="1.2"} 1
traefik_entrypoint_request_duration_seconds_bucket{code="499",entrypoint="websecure",method="GET",protocol="http",le="5"} 1
traefik_entrypoint_request_duration_seconds_bucket{code="499",entrypoint="websecure",method="GET",protocol="http",le="+Inf"} 1
traefik_entrypoint_request_duration_seconds_sum{code="499",entrypoint="websecure",method="GET",protocol="http"} 0.000376695
traefik_entrypoint_request_duration_seconds_count{code="499",entrypoint="websecure",method="GET",protocol="http"} 1
# HELP traefik_entrypoint_requests_tls_total How many HTTP requests with TLS processed on an entrypoint, partitioned by TLS Version and TLS cipher Used.
# TYPE traefik_entrypoint_requests_tls_total counter
traefik_entrypoint_requests_tls_total{entrypoint="websecure",tls_cipher="TLS_AES_128_GCM_SHA256",tls_version="1.3"} 47
# HELP traefik_entrypoint_requests_total How many HTTP requests processed on an entrypoint, partitioned by status code, protocol, and method.
# TYPE traefik_entrypoint_requests_total counter
traefik_entrypoint_requests_total{code="200",entrypoint="websecure",method="GET",protocol="http"} 33
traefik_entrypoint_requests_total{code="200",entrypoint="websecure",method="POST",protocol="http"} 3
traefik_entrypoint_requests_total{code="204",entrypoint="websecure",method="OPTIONS",protocol="http"} 3
traefik_entrypoint_requests_total{code="304",entrypoint="websecure",method="GET",protocol="http"} 6
traefik_entrypoint_requests_total{code="499",entrypoint="websecure",method="GET",protocol="http"} 1
# HELP traefik_service_open_connections How many open connections exist on a service, partitioned by method and protocol.
# TYPE traefik_service_open_connections gauge
traefik_service_open_connections{method="GET",protocol="http",service="covidpass-docker-compose@docker"} 0
traefik_service_open_connections{method="OPTIONS",protocol="http",service="covidpassapinet-docker-compose@docker"} 0
traefik_service_open_connections{method="POST",protocol="http",service="covidpassapinet-docker-compose@docker"} 0
# HELP traefik_service_request_duration_seconds How long it took to process the request on a service, partitioned by status code, protocol, and method.
# TYPE traefik_service_request_duration_seconds histogram
traefik_service_request_duration_seconds_bucket{code="200",method="GET",protocol="http",service="covidpass-docker-compose@docker",le="0.1"} 6
traefik_service_request_duration_seconds_bucket{code="200",method="GET",protocol="http",service="covidpass-docker-compose@docker",le="0.3"} 6
traefik_service_request_duration_seconds_bucket{code="200",method="GET",protocol="http",service="covidpass-docker-compose@docker",le="1.2"} 6
traefik_service_request_duration_seconds_bucket{code="200",method="GET",protocol="http",service="covidpass-docker-compose@docker",le="5"} 6
traefik_service_request_duration_seconds_bucket{code="200",method="GET",protocol="http",service="covidpass-docker-compose@docker",le="+Inf"} 6
traefik_service_request_duration_seconds_sum{code="200",method="GET",protocol="http",service="covidpass-docker-compose@docker"} 0.101081013
traefik_service_request_duration_seconds_count{code="200",method="GET",protocol="http",service="covidpass-docker-compose@docker"} 6
traefik_service_request_duration_seconds_bucket{code="200",method="POST",protocol="http",service="covidpassapinet-docker-compose@docker",le="0.1"} 2
traefik_service_request_duration_seconds_bucket{code="200",method="POST",protocol="http",service="covidpassapinet-docker-compose@docker",le="0.3"} 3
traefik_service_request_duration_seconds_bucket{code="200",method="POST",protocol="http",service="covidpassapinet-docker-compose@docker",le="1.2"} 3
traefik_service_request_duration_seconds_bucket{code="200",method="POST",protocol="http",service="covidpassapinet-docker-compose@docker",le="5"} 3
traefik_service_request_duration_seconds_bucket{code="200",method="POST",protocol="http",service="covidpassapinet-docker-compose@docker",le="+Inf"} 3
traefik_service_request_duration_seconds_sum{code="200",method="POST",protocol="http",service="covidpassapinet-docker-compose@docker"} 0.245780594
traefik_service_request_duration_seconds_count{code="200",method="POST",protocol="http",service="covidpassapinet-docker-compose@docker"} 3
traefik_service_request_duration_seconds_bucket{code="204",method="OPTIONS",protocol="http",service="covidpassapinet-docker-compose@docker",le="0.1"} 3
traefik_service_request_duration_seconds_bucket{code="204",method="OPTIONS",protocol="http",service="covidpassapinet-docker-compose@docker",le="0.3"} 3
traefik_service_request_duration_seconds_bucket{code="204",method="OPTIONS",protocol="http",service="covidpassapinet-docker-compose@docker",le="1.2"} 3
traefik_service_request_duration_seconds_bucket{code="204",method="OPTIONS",protocol="http",service="covidpassapinet-docker-compose@docker",le="5"} 3
traefik_service_request_duration_seconds_bucket{code="204",method="OPTIONS",protocol="http",service="covidpassapinet-docker-compose@docker",le="+Inf"} 3
traefik_service_request_duration_seconds_sum{code="204",method="OPTIONS",protocol="http",service="covidpassapinet-docker-compose@docker"} 0.105162933
traefik_service_request_duration_seconds_count{code="204",method="OPTIONS",protocol="http",service="covidpassapinet-docker-compose@docker"} 3
traefik_service_request_duration_seconds_bucket{code="304",method="GET",protocol="http",service="covidpass-docker-compose@docker",le="0.1"} 6
traefik_service_request_duration_seconds_bucket{code="304",method="GET",protocol="http",service="covidpass-docker-compose@docker",le="0.3"} 6
traefik_service_request_duration_seconds_bucket{code="304",method="GET",protocol="http",service="covidpass-docker-compose@docker",le="1.2"} 6
traefik_service_request_duration_seconds_bucket{code="304",method="GET",protocol="http",service="covidpass-docker-compose@docker",le="5"} 6
traefik_service_request_duration_seconds_bucket{code="304",method="GET",protocol="http",service="covidpass-docker-compose@docker",le="+Inf"} 6
traefik_service_request_duration_seconds_sum{code="304",method="GET",protocol="http",service="covidpass-docker-compose@docker"} 0.054989398999999994
traefik_service_request_duration_seconds_count{code="304",method="GET",protocol="http",service="covidpass-docker-compose@docker"} 6
traefik_service_request_duration_seconds_bucket{code="499",method="GET",protocol="http",service="covidpass-docker-compose@docker",le="0.1"} 1
traefik_service_request_duration_seconds_bucket{code="499",method="GET",protocol="http",service="covidpass-docker-compose@docker",le="0.3"} 1
traefik_service_request_duration_seconds_bucket{code="499",method="GET",protocol="http",service="covidpass-docker-compose@docker",le="1.2"} 1
traefik_service_request_duration_seconds_bucket{code="499",method="GET",protocol="http",service="covidpass-docker-compose@docker",le="5"} 1
traefik_service_request_duration_seconds_bucket{code="499",method="GET",protocol="http",service="covidpass-docker-compose@docker",le="+Inf"} 1
traefik_service_request_duration_seconds_sum{code="499",method="GET",protocol="http",service="covidpass-docker-compose@docker"} 0.000135744
traefik_service_request_duration_seconds_count{code="499",method="GET",protocol="http",service="covidpass-docker-compose@docker"} 1
# HELP traefik_service_requests_tls_total How many HTTP requests with TLS processed on a service, partitioned by TLS version and TLS cipher.
# TYPE traefik_service_requests_tls_total counter
traefik_service_requests_tls_total{service="covidpass-docker-compose@docker",tls_cipher="TLS_AES_128_GCM_SHA256",tls_version="1.3"} 13
traefik_service_requests_tls_total{service="covidpassapinet-docker-compose@docker",tls_cipher="TLS_AES_128_GCM_SHA256",tls_version="1.3"} 6
# HELP traefik_service_requests_total How many HTTP requests processed on a service, partitioned by status code, protocol, and method.
# TYPE traefik_service_requests_total counter
traefik_service_requests_total{code="200",method="GET",protocol="http",service="covidpass-docker-compose@docker"} 6
traefik_service_requests_total{code="200",method="POST",protocol="http",service="covidpassapinet-docker-compose@docker"} 3
traefik_service_requests_total{code="204",method="OPTIONS",protocol="http",service="covidpassapinet-docker-compose@docker"} 3
traefik_service_requests_total{code="304",method="GET",protocol="http",service="covidpass-docker-compose@docker"} 6
traefik_service_requests_total{code="499",method="GET",protocol="http",service="covidpass-docker-compose@docker"} 1
</details>
