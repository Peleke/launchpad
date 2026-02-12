# Email 3: Story / Credibility

**Subject**: The deploy that taught me why Kubernetes isn't always the answer
**Send**: Day 4
**Single job**: Build trust through shared experience

---

I deployed a side project to Kubernetes once. It was a simple CRUD app with maybe 10 users.

I spent 3 days writing Helm charts, configuring ingress, debugging service mesh issues, and setting up horizontal pod autoscaling for a service that would never need to scale past a single replica.

It worked. Technically. But I had spent more time on infrastructure than on the actual product. For 10 users.

Then I rewrote the whole thing as Lambda functions behind API Gateway. Deployed in 20 minutes. Cost dropped to literally $0/month on free tier. Handled the same 10 users perfectly.

That experience is why Module 6 (Serverless) comes before Module 8 (Kubernetes) in From 1 to Prod.

Not because serverless is better. Because when you learn serverless FIRST, you develop an instinct for when K8s is overkill. And that instinct is worth more than knowing how to write a Deployment manifest.

"When asking why specifically kubernetes and not serverless... they didn't know the answer." -- u/Gotxi, a hiring manager who rejected 11 of 12 candidates.

The answer isn't "K8s is better." The answer is "it depends on the workload" -- and you can only say that honestly if you've built with both.

That's what Module 6 and Module 8 give you.

If you're still on Module 1 or 2, keep going. The payoff is in the progression.

-- Peleke
