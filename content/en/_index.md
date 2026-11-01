---
title: Kli Docs
---

{{< blocks/cover title="Welcome to kli Documentation!" image_anchor="top" height="full" >}}

<img alt="kli Logo" class="mb-4" src="/img/kli-logo.svg" width="200" />
<br>

<div class="alert alert-warning text-start mx-auto mb-4" role="status" style="max-width: 42rem;">
  <strong>This project is archived and no longer maintained.</strong>
  These docs stay available as a reference.
</div>

<a class="btn btn-lg btn-primary me-3 mb-4" href="docs/">
  Learn More <i class="fas fa-arrow-alt-circle-right ms-2"></i>
</a>
<a class="btn btn-lg btn-secondary me-3 mb-4" href="docs/getting-started/">
  Getting Started <i class="fab fa-github ms-2 "></i>
</a>
</a>
<a class="btn btn-lg btn-secondary me-3 mb-4" href="docs/features/">
  Features <i class="fa-sharp-duotone fa-solid fa-feather"></i>
</a>


{{< blocks/link-down color="info" >}}
{{< /blocks/cover >}}

{{% blocks/lead color="primary" %}}

Kli is a unified CLI tool that simplifies the management of Kubernetes clusters across diverse cloud providers. Designed for developers, kli eliminates the complexity of multi-cloud Kubernetes setups by consolidating cluster management into one intuitive interface.

{{% /blocks/lead %}}

<!-- for the icons refer https://fontawesome.com/ -->

<!-- {{% blocks/section %}} -->
<!-- Problems in the Ecosystem -->
<!-- {.h1 .text-center} -->
<!---->
<!-- **Limited Customizability** -->
<!-- {.text-center} -->
<!---->
<!---->
<!-- **Multiple CLI Tools thus causing fragmentation** -->
<!-- {.text-center} -->
<!---->
<!-- **Users becomming dependent on a lot of tools instead of using a single tool** -->
<!-- {.text-center} -->
<!-- {{% /blocks/section %}} -->
<!---->
<!---->
<!---->
<!-- {{% blocks/section color="dark" type="row" %}} -->
<!-- {{% blocks/feature icon="fa-gauge-high" title="Fast" %}} -->
<!-- Creates Cloud-Managed or Self-managed HA cluster ~5 minutes -->
<!-- {{% /blocks/feature %}} -->
<!---->
<!-- {{% blocks/feature icon="fa-feather-pointed" title="Fast" %}} -->
<!-- No Dependencies. -->
<!-- Install and Ready to go! -->
<!-- {{% /blocks/feature %}} -->
<!---->
<!-- {{% blocks/feature icon="fa-wrench" title="Customizability" %}} -->
<!-- From Managed to Self-Managed -->
<!---->
<!-- From CNI Plugins to Pre-installed apps -->
<!-- {{% /blocks/feature %}} -->
<!---->
<!---->
<!-- {{% /blocks/section %}} -->
<!---->
<!---->

{{% blocks/section color="white" %}}

{{% alert color="warning" title="Archived" %}}
**This project is archived and no longer maintained.** These docs stay available as a reference. The code stays available under its original license.

What I build now:

- **[Kubmin](https://ksctl.com/product/kubmin)** — per-workload cost, efficiency, and SCI/SEI intelligence for Kubernetes
- **[infai](https://infai.dipankar-das.com)** — a terminal control plane for local LLM inference: one profile shape for llama.cpp and vLLM, many models at once, live tokens/sec plus CPU/RAM/VRAM telemetry, hardware fit checks before launch
- **[infaiw](https://infai.dipankar-das.com/infaiw/)** — a daemon-based agent harness: sessions keep running after you close the terminal, sidecar loops must pass an acceptance check before reporting back, every event lands on a durable branchable timeline, and approvals wait for you

**Want to take over maintenance of `kli`?** If you still depend on it and would like to become the maintainer, reach out on [Discord](https://discord.ksctl.com) or [open an issue](https://github.com/ksctl/kli/issues).
{{% /alert %}}

{{% /blocks/section %}}

{{% blocks/section type="row" %}}

{{% blocks/feature icon="fa-book" title="Docs stay up"
    url="docs/" url_text="Read the docs" %}}
The reference for kli is still here. The code stays available on GitHub under its original license.
{{% /blocks/feature %}}

{{% blocks/feature icon="fa-hammer" title="What I build now" %}}
[Kubmin](https://ksctl.com/product/kubmin), [infai](https://infai.dipankar-das.com), and [infaiw](https://infai.dipankar-das.com/infaiw/).
{{% /blocks/feature %}}

{{% blocks/feature icon="fab fa-discord" title="Take over kli"
    url="https://discord.ksctl.com" url_text="Reach out on Discord" %}}
If you still depend on it and want to become the maintainer, reach out on Discord or [open an issue](https://github.com/ksctl/kli/issues).
{{% /blocks/feature %}}

{{% /blocks/section %}}
