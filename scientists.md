# Applied Science Fiction: Operating a Research-Led Product

## Abstract

Scientists have increasingly become a part of many product teams, bringing many new skills to the table. This has been especially true in our augmented reality (AR) products, with our core computer vision pipelines being entirely researcher-led. With new opportunities comes new challenges, and we have had to adapt many of our SRE and product engineering practices to ensure everyone feels productive and supported. This talk shares the lessons we have learned in building a healthy and happy product team in a researcher-first environment.

## Long Description (abstract+)

The main thrust of the talk will be broken up between defining the problem space, successful guardrails we've built for the research teams to improve operability, internal tooling built so researchers can solve their own problems, and ways we've kept solid communication between disciplines. In the past we've had a split where scientists would develop a new algorithm and then hand it off to an engineering team to implement; by following these patterns we've been able to allow our research teams to push directly into production while ensuring uptime and customer happiness. This in turn improves our velocity and has taken a substantial burden off the other engineering groups.

## Takeaways

Tips, tricks, and ideas for how to improve interactions between SRE folks and researchers/scientists. Or at least an understanding of the unique challenges faced.

## Outline

* Intros
* DevSciOps
  * ML++
  * Needs
  * Wants
* Building Guardrails
  * CI
  * Static analysis
  * Code review
  * Deployment
    * Versioning
      * foo-latest
      * "works on my machine" no more
  * Runtime support
    * Worker architecture
      * Symbolic pipeline structure
      * Celery, Dagster
    * File sync
    * Retries
  * Testing weeks
* Tools and Observability
  * Research corpus
    * Staging
    * PII!
  * Django admin
  * Graphs and dashboards
* Communication
  * Brownbags
  * Team planning
  * OKR cycles
  * On call?
* Wrap up
