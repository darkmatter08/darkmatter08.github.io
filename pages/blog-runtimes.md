---
layout: page
title: Wrappers vs. Runtimes
description: Wrappers vs. Runtimes What Separates a Toy from a Breakout AI Product

---
<!-- <div align="center"><img src="/assets/media/investment_philosophy/illustration.jpeg" width="300" height="200" alt="Illustration" class="center"></div> -->

## **Wrappers vs. Runtimes: What Separates a Toy from a Breakout AI Product**

The LLM era has unleashed a tidal wave of new products. Every week, we see another AI-powered tool launch—each promising to save time, boost productivity, or reinvent an existing workflow.

But most of these tools get hit with the same critique:

**“It’s just a wrapper.”**

The implication is clear: it’s a thin shell over GPT, with no real moat, no proprietary tech, and no staying power.

Sometimes that’s true. But other times, it completely misses what makes a product great.

This post is about the difference between **wrappers**—products that look like AI but don’t really *do* much—and **runtimes**: systems that orchestrate LLMs, learn from users, and compound value over time.

Let’s explore what makes that difference matter.

### **Wrappers: Shallow Glue with Shallow Value**

A true wrapper startup is exactly what it sounds like: a basic UI that pipes user input into an LLM, maybe adds a bit of prompt engineering, and returns the output. Think “chatbot for X,” or “summarizer for Y.”

These tools are often useful in the short term, but fragile in the long term. Why? Because they don’t actually solve hard problems. They add convenience, not capability.

Take transcription apps built on top of OpenAI’s Whisper. Many are feature-light: record audio, send it to Whisper, return the text. These tools might have nice UX or integrations, but they’re easily replicable. If they don’t evolve, they become commodities.

Wrappers don’t learn. They don’t adapt. They don’t improve with usage. And so they don’t compound.

### **Runtimes: Systems That Learn and Adapt**

Now contrast that with a product like **Cursor**.

At a glance, Cursor is “just a wrapper” around GPT—an AI-powered code editor. But under the hood, it’s doing real systems engineering: using a custom FUSE filesystem to speed up code indexing, optimizing context windows across multi-file edits, and building devtools that preserve intent across iterative code changes.

More importantly, Cursor learns. It captures real-time user behavior—accepted completions, reverted edits, failed generations—and uses that feedback to improve prompts, model selection, and long-term personalization. Eventually, that data can inform model fine-tuning or even justify building proprietary models.

That’s not a wrapper. That’s a **runtime**: an evolving system that integrates with the user’s environment, learns from interaction, and orchestrates the model to produce more useful outcomes over time.

### **What Makes an AI Runtime?**

Here’s a working definition:

> A runtime is a system that embeds models into workflows in a way that adapts, improves, and compounds with user interaction.
> 

Wrappers are stateless.

Runtimes are stateful.

Wrappers are brittle.

Runtimes are robust.

Wrappers treat the model as the product.

Runtimes treat the model as a *component* in a larger system.

Great AI runtimes don’t just send a prompt and wait. They track context, maintain memory, orchestrate chains of calls, optimize latency, and learn from feedback loops. They’re built like infrastructure, not demos.

### Not just an “AI Feature”

Too often, we see SaaS tools bolt on AI as a feature—“smart reply,” “auto-summarize,” “magic fill.” These are *add-ons*, not architectures. A runtime is different: it doesn’t just decorate a workflow with AI - it **redefines** the workflow around AI. In a runtime, the model is embedded at the core of how the product operates, learns, and delivers value. The interface, the data model, the infrastructure - everything bends around the assumption that the system is dynamic, probabilistic, and evolving.

This isn’t “SaaS with AI.” It’s software built *for* AI from the ground up.

### **The Feedback Flywheel**

In traditional SaaS, we talk about product-led growth and usage-based moats. In AI, runtimes create their own version of this: a **feedback flywheel**.

- The more a runtime is used, the more data it gathers about user preferences, model performance, and task-specific challenges.
- That data can be used to improve the product - better prompts, smarter routing, fine-tuned models, more helpful suggestions.
- Which leads to more usage, deeper engagement, and better outcomes.

This flywheel is why seemingly simple tools like Cursor or Windsurf can become defensible, even if they rely on foundation models they didn’t train themselves.

Outside of coding tools, we see similar patterns in Notion and Perplexity. Platforms with significant user-generated content are great places to spin the flywheel faster and faster.

Anti-flywheels exist too. High-touch, relationship driven orgs often become worse with scale. McKinsey is actually shrinking headcount, while OpenAI has scaled its team 10x in a few years. Feedback flywheels scale, people don’t.

### **Why Runtimes Are Durable**

What makes runtimes durable, even when they don’t own the underlying model?

- **Workflow Depth**: Runtimes live inside real workflows. The closer they get to where work is done, the harder they are to replace.
- **Systems Investment**: Great runtimes solve hard technical problems - memory management, latency, context switching, evaluation - under the hood. These improvements enable the AI layer to operate more effectively - faster iteration, more relevant context, and better user ergonomics.
- **Learning Loops**: Runtimes get better over time. Wrappers don’t.
- **Model Agnosticism**: As the model layer continues to evolve, runtimes are in a position to choose the best one for each task—or even train their own when the economics make sense.

### **The Investor View**

As an investor, I'm not put off by products that *look* like wrappers. I dig deeper to ask: is this company on a path to becoming a runtime?

I ask:

- What is this system learning from its users?
- How tightly is it embedded in a real workflow?
- How fast does the feedback loop spin?
- Could this product support its own model, if needed?

The great LLM-native companies won’t win by accessing GPT. They’ll win by orchestrating it. Evolving it. Wrapping it in context, feedback, and infrastructure until the user barely sees the model at all.

Because in the end, it’s not the model that matters. It’s the runtime.
