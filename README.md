# Eric Del Orefice

Cyber Security and Game Design senior at High Point University. Air Force ROTC cadet, commissioning
into the U.S. Space Force in spring 2027.

I build agent systems that run unattended against real services, and I spend most of my time on
what they get wrong quietly.

## What I am working on

**One defect, ten frameworks.** A storage or search backend fails, and the adapter above it reports
an empty result instead of an error. The caller sees "no documents" and carries on. I have been
finding this in the storage, vector-store and config layers of the major open-source agent
frameworks and sending fixes upstream, each with a reproduction and a test that fails on the old
code.

- [deepset-ai/haystack-core-integrations](https://github.com/deepset-ai/haystack-core-integrations/pulls?q=author%3Aericdelorefice) - **both merged**: a Qdrant backend failure was reported as an empty result, and in pgvector an empty filter deleted the whole table and called it a match
- [agno-agi/agno](https://github.com/agno-agi/agno/pulls?q=author%3Aericdelorefice) - an async `delete_run` that failed reported the run as missing, where the sync twin in the same backend raises
- [browser-use/browser-use](https://github.com/browser-use/browser-use/pulls?q=author%3Aericdelorefice)
- [camel-ai/camel](https://github.com/camel-ai/camel/pulls?q=author%3Aericdelorefice)
- [aurelio-labs/semantic-router](https://github.com/aurelio-labs/semantic-router/pulls?q=author%3Aericdelorefice) - **merged**: a failed Qdrant scroll was reported as an empty index, and with `auto_sync="remote"` that deleted every local route the reply omitted
- [microsoft/semantic-kernel](https://github.com/microsoft/semantic-kernel/pulls?q=author%3Aericdelorefice)
- [run-llama/llama_index](https://github.com/run-llama/llama_index/pulls?q=author%3Aericdelorefice) - a Cosmos DB delete that could never have run reported the key as absent, and a throttled Tablestore read came back as "no such key"
- [crewAIInc/crewAI](https://github.com/crewAIInc/crewAI/pulls?q=author%3Aericdelorefice)
- [sardine-ai/mcp-server-manager](https://github.com/sardine-ai/mcp-server-manager/pulls?q=author%3Aericdelorefice)

**[unattended-agent-security](https://github.com/ericdelorefice/unattended-agent-security)** - ten
failures from running an LLM agent unattended against live systems, the controls that prevent them,
and a one-page deployment checklist. Nine of the ten reported success while failing.

## How I work

A check that has never gone red proves nothing. Before I trust a fix I make the test fail against the
old code, read why it failed rather than that it failed, and go back to any sentence that says "not a
problem" and find out what would have to be true for it to be wrong.

## Elsewhere

- [LinkedIn](https://www.linkedin.com/in/eric-del-orefice-632626286/)
- Azure Fundamentals (AZ-900) - exam booked for 30 September 2026
- Interested in cyberspace operations, agent reliability, and the gap between a system that reports
  success and one that succeeded
