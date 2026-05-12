# Karsa

Linux runtime observability and anomaly analysis toolkit — built on eBPF.

Karsa is for when logs aren't enough. Instead of static metrics or signature-based alerts, it focuses on *what's actually happening at runtime*: which process triggered what, what changed before it, and whether the behavior looks anomalous.

---

## What it does

Karsa instruments the Linux kernel at runtime using eBPF to collect behavioral telemetry with minimal overhead. It's not a SIEM. It's not a dashboard. It's a visibility layer — designed for researchers and operators who need to understand system behavior as it happens.

On the observability side, Karsa traces process execution across the full process tree, attaches syscall-level visibility per process, and surfaces daemon and service activity in context. On the analysis side, it correlates CPU, memory, and network events back to the process that triggered them — so resource anomalies aren't just numbers, they're attached to behavior.

The behavioral analysis engine looks for runtime patterns associated with privilege escalation, persistence mechanisms, anomalous process execution, and exploit-triggered activity. It doesn't rely on signatures — it watches how processes behave over time and flags deviations.

---

## Why not just use existing tools?

Most monitoring tools answer: *what is the system doing?*  
Karsa tries to answer: *why is it doing that, and is it normal?*

When CPU spikes, Karsa doesn't just log the spike — it surfaces what process caused it, what syscalls it made, and whether its behavior deviates from what's expected. The goal is runtime transparency, not just metric collection.

It's particularly useful during privilege escalation investigations, post-exploitation behavior analysis, persistence mechanism research, and exploit-triggered runtime anomaly analysis.

---

## Requirements

Linux kernel ≥ 5.8 (for full eBPF feature support), `CAP_BPF` or root privileges, `libbpf`, `bpftool`.

---

## Status

> Work in progress. Core telemetry pipeline and eBPF probes are functional. Behavioral analysis engine is under active development.

---

## License

MIT
