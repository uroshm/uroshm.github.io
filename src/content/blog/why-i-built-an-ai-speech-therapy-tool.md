---
title: "The Forgotten AI Use Case"
description: "What the research says about apps in speech therapy, and why I think AI should be helping kids who need it practice speech."
pubDate: 2026-08-26
---

Scroll LinkedIn for five minutes and you'll find a dozen vague posts about "AI for good," "AI for humanity,", and more. They rack up likes, a few clapping-hands emojis -  and then nothing happens.

If you want to know why speech
therapists are slow to adopt software, and what it would take to change that, the answers are
mostly already published.

Models that can listen to a child say a word and
tell you how close they got already exist. Automated end-to-end solutions that help build a personalized learning experience do not.

## The problem, briefly

Modern web apps have changed a lot of fields, and speech-language pathology (SLP) is no exception. 

- real-time intelligent feedback 
- personalized learning
- secure-by-design data management
- domain built from the ground-up by those in the know (i.e. SLPs)

That combination is what makes personalized, tailored tools for Speech Sound Disorders (SSDs)
possible in a way they weren't before. And it's not like remote therapy is a new idea. As Roper and
Skeat (2022) put it, "Telehealth has existed since at least the 1960s, and has included SLP
services since at least the mid-1970s" (p. 528). Distance care has been an option for half a
century. Adoption is still low.

There are a few adjacent products out there. Sonde Health uses AI to analyze speech for general
health monitoring, but it isn't aimed at SSDs. Speechelo gives clients examples of correct speech,
but it lacks the data governance and interactivity that actual learning requires. As far as I can
tell, no web application currently puts all of these together: a modern web stack, real-time
generative AI analysis of speech, robust privacy protection, and administrative automation.

I decided to build one. But first, here is what the literature says.

## What the research actually says

### Kids need interaction, and rewards work

Interactive features aren't decoration when your patients are children. Heyman (2020) points out
that "interactive features in an app can draw the child's attention to particular content. This
can be used to provide support and scaffold the learning" (p. 307). This is classic pedagogy, and it
improves a child's ability to process speech and represent information cognitively.

Motivation matters too. Heyman (2020) notes that "The use of external rewards is particularly
beneficial to increase motivation and performance on tasks that have low initial interest"
(p. 308). Game tokens, streaks, whatever keeps a kid coming back. A product can be as educational as
you like, but nobody learns from software they stop opening. This principle usually gets applied to
games, but there's no reason speech tests can't borrow from it.

### ...but don't overdo it

The counterweight: "in order to effectively use apps for language intervention, it is necessary to
consider the potential impact that the use of apps has on processing of information and working
memory" (Heyman, 2020, p. 307). Learning happens in a brain with finite working memory. The app
should stimulate just enough to keep the client engaged, without burying the actual work under
gamification and distractions. Efficient learning is a balance between stimulation and disciplined
focus.

### Mobile tech reaches kids who can't get to a clinic

Access to speech therapy depends a lot on where you live and what you can afford. Some kids have
an SLP at their school. Others are in a rural area, or their family doesn't have coverage, or the
one SLP in the district is stretched across far too many students. Those kids mostly get a word
list and whatever practice a busy parent can manage.

This is where software can actually help. Benedon (2018) found that "mobile technologies have been
found to increase autonomy, improve productivity, enhance interprofessional communication, and
permit efficient access to occupation-relevant data in the workplace." The autonomy part is what I
find most compelling. An app that runs on a phone works the same in a town with no clinic as it
does in a well-funded suburb. Benedon (2018) also expects "increased rates of use of mobile tools
to support administration of care and patient education in healthcare settings." A tool that can
listen and give feedback between appointments, or in place of appointments that aren't happening,
is useful to exactly the kids who have the least access.

Speech sound disorders are common, and there are far more kids who need practice than
there are therapist hours to go around. It's just not a flashy use of AI. It doesn't demo well on a
stage the way a chatbot or an image generator does. That's fine with me. It was a big part of why I
wanted to work on it.

### SLPs are hesitant, and knowing the benefits isn't enough

Here's the uncomfortable part. Clinicians themselves are slow to adopt this stuff. "They are faced
with the task of constantly adapting to a changing field and finding their own role and identity in
the midst of this transformation" (Szabó et al., 2022). Whether it's fear of being replaced or just
unfamiliarity with new tech, paper after paper echoes the same thing: SLPs are uncomfortable using
web applications. And crucially, research "clearly shows that the knowledge about the potential
advantages of using apps is not sufficient to use them" (Szabó et al., 2022, p. 388). You can't
just present the benefits and expect adoption. There's real work to do in showing clinicians how
these tools fit into their day.

### Privacy is the biggest concern, and rightly so

"Data privacy concerns are well reported among health-related apps and digital tools, especially
considering the vast amounts of sensitive health-related and personal information that can be
collected through such means" (Lin et al., 2022, p. 11). Web apps are newer and less regulated than
traditional therapy, so both clinicians and clients worry about where their data goes. HIPAA (the
Health Insurance Portability and Accountability Act of 1996) exists precisely for this. Any tool
that wants traction with speech-language professionals has to meet that bar, both legally and
ethically.

Practically, that means modern web security practices, zero trust architecture,  and encryption
of test data and client information so that even a breach doesn't expose anything useful. Multiple
studies list security as a primary stakeholder concern, so it has to be a priority from the start
rather than something bolted on later.

### AI and ASR are already here

ChatGPT, Gemini, DeepSeek, and friends have reshaped the technology landscape, and combining them
with automatic speech recognition (ASR) could change how SLPs deliver therapy. Some products already
use "techniques such as machine learning, deep learning, signal processing, and linguistics to
analyze and understand human speech. ASR technology can potentially be used in speech therapy to
support individuals living with SSD" (Deka et al., 2025, p. 2). The specific strengths are
"understanding spoken language, identifying objects and patterns, making decisions, and solving
problems" (Deka et al., 2025, p. 2).

What surprised me most: the machines can be more objective than the humans. In one study,
"caregivers were lenient in their evaluation or had difficulty in identifying mispronunciations. In
contrast, the automated algorithm exhibits superior ability to detect mispronunciations compared to
correct pronunciations" (Deka et al., 2025, p. 17). Caregivers and even SLPs tend to be forgiving.
An algorithm isn't.

### The incumbent: SLP Toolkit

One of the most widely used tools among SLPs today is [SLP Toolkit](https://www.slptoolkit.com),
a web platform with screening instruments, progress monitoring, data collection, goal-setting
frameworks, and report generation. It's good at what it does, but what it does is administration.
It's a management utility, not a treatment platform. It doesn't use AI, automated speech analysis,
or adaptive intervention recommendations, any of which could support both clinical decision-making
and the therapy itself.

## What I built: Listen

Listen tries to fill those gaps: near real-time speech analysis with AI-generated feedback, a
secure database for persistence and reporting, all open source. The front-end integrates
standardized SLP assessments, with images and prompts designed to make practice feel like learning
rather than testing. A patient records their pronunciation, the audio is analyzed and sent to a
generative model (DeepSeek or ChatGPT, for example), and the feedback comes back to the front-end
where the SLP or patient can copy it straight into documentation or billing reports.

<!-- TODO: add Figure 1, the implementation flow chart, here once it's in src/assets -->

Right now there's one implemented assessment: articulation of the /s/ sound, with word selections
covering the initial, medial, and final positions. The AI compares the user's pronunciation to the
expected standard and returns feedback in real time. That feedback is copyable, which sounds
trivial but is the whole point: less time writing reports, more time with the patient.

Under the hood, the database is Postgres. User passwords are hashed with
[BCrypt](https://bcrypt.online/). Audio samples are currently stored as
[BLOBs](https://docs.oracle.com/javase/8/docs/api/java/sql/Blob.html). Encryption of patient PII
and the audio itself is on the roadmap, not done yet, and I'd rather say that plainly than pretend
otherwise.

And it's open source. Given everything above about maintenance and design-in-isolation, this felt
non-negotiable. Anyone can contribute, and more importantly, SLPs and other stakeholders can shape
the tool directly instead of being consulted after it ships.

## How it's going (honestly)

Listen has not been formally evaluated with a representative sample of practicing SLPs. The
testing so far has been with my spouse, who is a licensed SLP, and several of her colleagues. Their
feedback has been invaluable for early development, but anecdotal feedback is not a usability study,
and it's certainly not a clinical trial. That's the biggest limitation of this work so far, and
formal validation is the main thing standing between this and something you could responsibly use
in a clinic.

With that caveat firmly in place: the informal feedback has been very positive. The SLPs who tried
it estimated roughly a 70% time savings, mostly on administrative work. They named report writing,
test scoring, and creating testing materials as the most time-consuming parts of their job, and
Listen automates all three: administering the assessment, generating the report, and scoring the
results.

They also had criticisms, which is the useful part. One articulation test isn't enough to really
evaluate the tool, and they want more assessments. And while they found the generative AI output
impressive, the accuracy isn't at clinical expectations yet. Better model selection and prompt
engineering should help there.

## What's next

As the technology evolves, SLPs, developers, and clients have to build this together, with the
ethical concerns front and center. Done thoughtfully, tools like Listen could genuinely change
speech therapy for the next generation of kids who need it, including the ones who don't
currently have much access to it.

Concretely, the next iteration should:

- run formal usability testing with 10+ practicing SLPs
- expand assessments beyond the /s/ sound
- encrypt patient PII and audio samples

If any of this interests you, the project is open source and I'd love the help.

## References

Attwell, G. A., Bennin, K. E., & Tekinerdogan, B. (2022). A Systematic Review of Online Speech
Therapy Systems for Intervention in Childhood Speech Communication Disorders. *Sensors, 22*(24),
9713. [https://doi.org/10.3390/s22249713](https://doi.org/10.3390/s22249713)

Benedon, T. A. (2018). *Speech-Language Pathologists' Practices and Attitudes Toward App Use in
Therapy* [M.S., The University of Wisconsin - Milwaukee].

Deka, C., Shrivastava, A., Abraham, A. K., Nautiyal, S., & Chauhan, P. (2025). AI-based automated
speech therapy tools for persons with speech sound disorder: A systematic literature review.
*Speech, Language and Hearing, 28*(1), 2359274.
[https://doi.org/10.1080/2050571X.2024.2359274](https://doi.org/10.1080/2050571X.2024.2359274)

Heyman, N. (2020). Identifying features of apps to support using evidence-based language
intervention with children. *Assistive Technology, 32*(6), 306-316.
[https://doi.org/10.1080/10400435.2018.1553078](https://doi.org/10.1080/10400435.2018.1553078)

Lin, Y., Lemos, M., & Neuschaefer-Rube, C. (2022). Digital Health and Learning in Speech-Language
Pathology, Phoniatrics, and Otolaryngology: Survey Study for Designing a Digital Learning Toolbox
App. *JMIR Medical Education, 8*(2), e34042.
[https://doi.org/10.2196/34042](https://doi.org/10.2196/34042)

Roper, A., & Skeat, J. (2022). Innovation through participatory design: Collaborative qualitative
methods in the development of speech-language pathology technology. *International Journal of
Speech-Language Pathology, 24*(5), 527-532.
[https://doi.org/10.1080/17549507.2022.2050943](https://doi.org/10.1080/17549507.2022.2050943)

Szabó, B., Dirks, S., & Scherger, A.-L. (2022). Apps and Digital Resources in Speech and Language
Therapy - Which Factors Influence Therapists' Acceptance? In M. Antona & C. Stephanidis (Eds.),
*Universal Access in Human-Computer Interaction. Novel Design Approaches and Technologies* (Vol.
13308, pp. 379-391). Springer International Publishing.
[https://doi.org/10.1007/978-3-031-05028-2_25](https://doi.org/10.1007/978-3-031-05028-2_25)
