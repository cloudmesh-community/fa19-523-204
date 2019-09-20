# Assignment 2 fa19-523-204
| Andrew C. Dingman
| adingman@indiana.edu
| hid: fa19-523-204

# Summary

The week two videos are primarily motivational in nature, essentially
making a case for caring about big data. The videos use several Gartner hype cycle
reports as a source of information on trends of current and historic
interest. Following that, they discuss a number of cloud, big data, and
AI/Machine Learning trends over recent years, looking both at
currently "hot" technologies and and the evolution of the hype cycle
projects and real world adoption outcomes. They then digress into job
opportunities, before discussing computing models and research
paradigms, and wrap up with some examples of real-world big data use
cases.

## Hype Cycle

The hype cycle is an interesting tool for understanding the progress
of a technology toward utility and/or obsolescence, and the collection
of Gartner reports placing technologies on that cycle over time was
interesting. I was, however, very surprised to be left with the
impression that the course author essentially considers a technology
dead and of no further interest when it reaches the "plateau of
productivity". Working in industry, the point at which I have
generally been most interested in adopting a technology has been when
I deem it to be on the plateau, or at the very least well onto the
"slope of enlightenment".

Running enterprise IT, I do not want to invest time and money in
developing capabilities around a technology that may never reach a
point of delivering improved productivity for my users. Something that
is coming out of the trough of disillusionment and has a long period
of boring utility ahead of it is far more interesting than something
climbing the first slope or near the peak. The bar for those to
convince me to pay attention is much higher; it has to be very obvious
that it offers benefits specific to my business.

That equation is a bit different for career development. Getting in on
Linux and Open Source nearer the "technology trigger" phase in the
late 90s did position me well to build a successful career on that
foundation. Even then, if the timing of real industry adoption had
been slightly different I could easily have seen no benefit from the
choice. Perhaps it's different in academia, where the interest in your
papers and curriculum may well wane by the time the technology is
consumable for industry, but it's definitely not the perspective I'm
used to.

## Trends

The discussion of big data trends seemed largely old hat. As was
mentioned in the presentations, many of the points raised to
illustrate the explosion of available data generated, gathered, and
stored have been going on so long that the producers of the graphs
have gotten bored with them and stopped producing. Perhaps it's
because I worked at a fortune 500 software company for over a decade,
but I pretty much thought everyone knew about the exponential growth
of data, storage, and compute.

The discussion of cloud technology seemed more relevant. Not much of
it was new to me, but it still covered things I find I have to explain
to customers and clients, rather than things I expect them to
know. The ideas of public, private, and hybrid cloud systems,
differences between IaaS, PaaS and SaaS, and related changes in how
companies develop new capabilites are definitely still live and
interesting issues.

Most of those seem to me to be well onto the slope
of enlightenment, but not thigs I'd assume students in an introductory
big data class know. Cloud availability of tools like tensor
processors and GPGPU chips is very new and interesting to me. Still
early enough in deployment that I wouldn't feel comfortable
recommending them to most customers because I'm not yet confident I
know where they do and don't offer benefits. Hopefully I'll know more
toward the end of this course.

The change in research paradigms was, for me, the most interesting
topic covered. Although I feel like I've heard at least parts of it
before, the difference between the 3rd paradigm, generating carefully
chosen data to test previously-developed theories, and the 4th,
examining copious data to look for signs of potential theories, is
fascinating. In some sense, it almost seems like a more powerful
return to the earlier "observation" paradigm, but with much greater
power.

Beyond excitement at the possibilities, my initial thought on this
transformation is concern that the same computational power that
allows us to search for patterns in vast amounts of data may also lead
us astray. There seems to be a huge potential for spurrious
correlations or happenstance in the data sets to produce a problem
much like the well-known issues of *p-hacking*, but on a grander
scale. Since that could also happen without the participation of a
human who can inspect their own behavior and motivations, it seems all
the more important to develop a testable theory from the data.

I'm not terribly familiar with the field, but it seems that perhaps
fields like astrophysics that still depend heavily on observation
without much possibility of experimentation could both benefit greatly
and guide the rest of us in avoiding those pitfalls.

# Subtopic: Trends in cloud processing technology

The current cloud platforms of which I am aware, both public and
private, are almost exclusively deployed on x86-64 hardware with
virtualization extensions. In the public space, Azure uses Hyper-V,
Amazon uses Xen, a few niche players use VMWare, and Googgle Compute
Engine along with most providers I haven't mentioned use Linux
KVM. Many also use container technologies like Kubernetes, Docker,
Podman, and similar on top of the VMs, but the underlying computation
is still on Intel-compatible chips.

In this week's lectures, it was pointed out that for big data
applications, this dominant platform may not be the ideal. Mention was
made of tensor processors and of GPUs such as those developed by
nVidia as more effective for some classes of problems, and the recent
availability of such chips in cloud contexts. The solutions I'm
currently aware of involve dedicating individual GPU chips from
dedicated many-GPU platforms to particular vloud VM instances, which
rather reduces the flexibility normally expected from cloud systems.

I have also recently heard discussion of certain classes of my
customers looking for CPU diversity as a security measure. They hope to reduce
the liklihood that a particular exploit is successful when those
exploits may depend on details of the physical architecture to execute
successfully, even when taking advantage of the same software
vulnerability at a source code level.

While these applications contrast with the cases from the lecture in
that the advantage they seek is *unpredictability* of the
characteristics of the execution platform, the idea of processor
diversity seems similar. A system which could unpredictably move
workloads between hardware platforms should also be able to
deliberately do so for performance optimization.

# Possible improvements

For use in a cloud platform, I know that both Power64 and Arm64 now
offer virtualization capabilities which can be used through the same
KVM hypervisor as x86-84 chips. Are there similar developments
happening in the area of tensor processors or GPUs to provide these
capabilities through standard interfaces? Is there demand for these
services? what kinds of new processing could be enabled by a cloud
platform that made these capabilites available?

