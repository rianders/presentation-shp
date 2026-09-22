# Chameleon Cloud: Background for Stage 2

Reference notes, not slide content. Checked 2026-09-21.

## Rick's framing

- It's cloud infrastructure, not supercomputer infrastructure, so it fits the research and student work more closely than Amarel.
- It's the better option. It's not hard to get people into.
- Rutgers has no direct agreement. Access runs through the NSF research community.
- Rick automated the environment with AI agents, which made IT management easier.

## Facts

- **What it is:** An NSF-funded testbed built on OpenStack. A $12M Phase 4 award brings total funding past $42M. H100 GPUs are planned, and NCAR is becoming a full site.
- **Resources:** Bare-metal machines you can reserve and reconfigure, KVM virtual machines, GPUs (including A100), and edge devices through CHI@Edge.
- **Who can be PI:** Faculty, research staff, and educators at accredited schools. Students can't be PIs, but PIs add them to projects.
- **Login:** Globus Auth with institutional InCommon accounts, Google, or Globus ID.
- **Allocations:** New projects start with 20,000 service units for six months. One unit is one hour on a base bare-metal server. Requests are typically processed within one business day. The FAQ implies there's no cost to approved projects but doesn't say so outright.
- **Automation:** OpenStack command line, Jupyter notebooks, Heat for multi-machine setups, custom images, and Trovi for sharing complete environments.
- **Teaching:** Instructors share their labs. Austin Community College ran 14 courses with 420 students on it.
- **Limits:** It expects openly published research. The docs say nothing about HIPAA or PHI, so treat it as off-limits for patient data and confirm with the help desk.

## Sources

- https://chameleoncloud.org/learn/frequently-asked-questions/
- https://chameleoncloud.readthedocs.io/en/latest/user/pi_eligibility.html
- https://chameleoncloud.readthedocs.io/en/latest/
- https://chameleoncloud.org/education/
- https://www.chameleoncloud.org/blog/2024/08/01/chameleon-testbed-secures-12-million-in-funding-for-phase-4/
