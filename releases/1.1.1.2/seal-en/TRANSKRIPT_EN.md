# 1.1.1.2 — Invoice common test, group 2 · English transcript

One sentence per line. Voices: `[VOICE:HOOK]` hook, `[VOICE:NARRATOR]` narrator, `[VOICE:CLOSER]` closing. 118 sentences; English sentence N = Turkish sentence N. Letters and versions are spelled for the voice (e.g. 'L-L-M', 'Q four').

## KANCA

[VOICE:HOOK] [PARAGRAPH:kanca]
We are on day two of our common test engine arena, and this time the three models in our second group have stepped into the ring.
In this group, two models from the same company, identical in size, go head to head.
While the older version reads seventy-seven of the two hundred invoices accurately, the new version gets one hundred sixty-one right.
On degraded invoices, where pure software holds on to fifty-five, the new version reads one hundred three accurately.
Even though the common test is built to catch errors rather than squeeze out peak performance, we still got striking results.
Let's examine them together.
Let's begin!

## GİRİŞ

[VOICE:NARRATOR] [PARAGRAPH:turnusol]
For those arriving at our channel straight from a test video, perhaps after searching for a model name, let's state one thing up front: the common test works like litmus paper.
We give every model the same prompt, the same rules, and the same output format; our goal isn't to condemn a model, but to see where each model gets stuck and separate whether the cause is the model itself or the package we built around it.
That's why some low scores come not from a model's reading ability, but from the answer not being packaged in the format we expected; wherever we spot these, we mark them one by one.
Models that get stuck in the common test will be tested again in upcoming custom test videos, with our test engine tuned specifically for each model.

[PARAGRAPH:hesap]
First, let's lay out the rules of this test so we can read the results together.
In the Document Scanning branch of L-L-M Test Office, three models entered the second common test on invoices.
We gave all three models the exact same two hundred invoices that the first group of models saw.
That way, any difference between two models comes from the model itself, not from the invoices.
We divided the test into two tiers.
In the first tier, we asked for five basic pieces of information from the invoice: invoice number, date, seller, tax, and total.
In the second tier, we asked for the entire invoice, including all of its line items.

[PARAGRAPH:puan]
We use two different scoring systems.
The first is the strict system.
We require the correct answer in a specific format.
For an application built around a model to run without issues, models must follow that format requirement.
The second is the flexible system.
In this system, we check whether the content is right without getting hung up on format requirements.
These two readings give us valuable insight into both a model's capabilities and the kind and amount of software support it needs.
To take the comparison one step further, we also ran pure software and included its one hundred forty-two correct reads on two hundred clean invoices in the overall evaluation.

[PARAGRAPH:ortam]
Testing was carried out on our Asus ProArt H-N seven-three-zero-six laptop, plugged into power and set to manual mode with all power settings kept at maximum.
We will share not only accuracy results from our measurements, but speed data as well.
Because we ran this group two days after the first group, we also ran a control experiment to test whether the power setting affected speed, and confirmed there was no difference at all.

## MODELLER

[VOICE:NARRATOR] [PARAGRAPH:modeller]
There are three models in this group; two are the old and new versions from the same family, and the third is the largest model in the group.
We ran all three with Q four quantization under the exact same settings.

[PARAGRAPH:lfm2]
The first model was L-F-M two, a one point two billion parameter model from Liquid A-I.
In our easy test asking for the basic fields, the model read seventy-seven of the two hundred invoices accurately.
While most of its errors were wrong values, on twenty-five invoices it also added extra fields we hadn't asked for; we asked for five pieces of information, and the model wrote more.
Reading forty-six invoices per minute, this model didn't get a single invoice right in the hard test where we included all information on the document; since on most invoices it omitted some of the requested fields altogether, its flexible score stayed at zero too.

[PARAGRAPH:lfm25]
Our second model is the new version from the same family, L-F-M two point five.
It is the exact same size as the first model, containing one point two billion parameters.
In our easy test, the model read one hundred sixty-one of the two hundred invoices accurately, reaching eighty percent and pulling ahead of pure software.
With that, it earned the highest score in the easy test among all seven models we have measured so far.
Its output format didn't break on a single invoice, all thirty-nine errors were value errors, and it read fifty-nine invoices per minute.
In the hard test, on the full-invoice reading task across two hundred invoices, it extracted twelve without a single flaw.
With that result, it beat SmolLM two's four correct reads from the first group and posted the highest hard-test score so far.

[PARAGRAPH:surum_farki]
When we place the two versions side by side, the number of accurately read invoices more than doubled.
What is even more instructive is how the error types changed: the twenty-five invoices where the older version wrote extra fields dropped to zero in the new version, and all broken outputs disappeared.
In other words, the new version doesn't just find more right answers; it also follows instructions much better.
Since the size and architecture stayed identical, the source of the difference is the version update; which part of the training changed is something we cannot tell from this measurement.

[PARAGRAPH:qwen3]
Our third contender is the largest in the group: Qwen three from the Qwen family.
Its name points to one point seven billion parameters.
In our easy test, it read ninety-nine of the two hundred invoices accurately, stopping just shy of fifty percent.
On eight invoices it got caught on a packaging error because it wrapped the right answer inside code markers; under flexible scoring, its correct count rises to one hundred seven.
When we inspected the model's broken outputs one by one during our engine-freezing runs and in the noisy test, we saw that even though we had turned thinking mode off, a thinking tag leaked into roughly half of the broken answers.
That too is a packaging issue rather than a reading failure, and it will be one of the first things we address in the custom test video.
At thirty-seven invoices per minute, Qwen three was the slowest in the group.
In the hard test, it produced five successful reads out of two hundred invoices.

[PARAGRAPH:taban_esleme]
Here we paused and returned to the question we asked in the first video: do the model and pure software get stuck on the same invoices?
There were forty-four invoices that the new version, L-F-M two point five, read accurately while pure software missed them.
The number of invoices that pure software read accurately while the model missed them is twenty-five.
In the first group, we hadn't found a statistically significant difference between the models and pure software on clean text; here, the difference came out in the model's favor and passed our statistical test as well.
Thus, L-F-M two point five became our first model to statistically outperform rule-based pure software on clean invoices.
For the other two models, the picture flips; both the older version and Qwen three missed a sizable share of the invoices that pure software read.

## GÜRÜLTÜ

[VOICE:NARRATOR] [PARAGRAPH:gurultu_neden]
Now we are at the exact point where A-I models shine.
Because the seventy-one percent score that pure software got on clean text dropped to unacceptable levels once noisy text came into play, meaning when real-world scenarios that had passed through a scanner landed on our desk.
We are now going to see how the models in this group answer the question we asked in our introduction video, after the first group: can a small model fill the gap in between?

[PARAGRAPH:gurultu_kural]
When degrading the invoices, we kept the exact same rule.
We only swapped look-alike characters with one another: zero with capital O, one with lowercase L or capital I, and five with the letter S.
We never turned one digit into another digit.
Had we done that, the information on the invoice would have been destroyed, and neither a model nor a human could have found the right answer.
We didn't erase the information, we only disguised it; the true answer for every invoice remains unchanged.
Then, in the first tier, we had the three models and pure software read the degraded versions of those same two hundred invoices.

[PARAGRAPH:gurultu_taban]
Let's look at pure software again.
Pure software read one hundred forty-two of the two hundred clean documents.
When the text became noisy, however, it could hold on to only fifty-five of the two hundred invoices.
Rule-based software stops the moment it can't find the pattern it expects; the instant it sees the letter O where a zero should be, it misses that invoice.

[PARAGRAPH:gurultu_lfm25]
We put the models through the noisy test.
The new version, L-F-M two point five, read one hundred three of the two hundred invoices accurately.
The model was affected by the noise too, but nowhere near as severely as pure software.
We don't give a numerical speed comparison here; because clean and noisy text have different inputs and were run on different days, such a comparison could be misleading.
When we checked the documents entering the test one by one, there were sixty-one documents that pure software failed to read but the model got right, whereas the reverse happened on only thirteen documents.
The gap, which was nineteen on clean documents, widened to forty-eight once noise entered the picture, passing our statistical test by a wide margin.
In short, at this noise level, a one point two billion parameter model closed a major share of pure software's gap.

[PARAGRAPH:gurultu_digerleri]
For the other two models, the picture isn't nearly as clear.
The older version, L-F-M two, read fifty-six of the two hundred noisy documents accurately, finishing neck and neck with pure software.
Qwen three edged slightly ahead of pure software with sixty-eight accurate reads, but the difference was not statistically significant.
When we look at these alongside the first group's noisy results, the overall picture comes into focus.
With one hundred three accurate reads, L-F-M two point five achieved the highest noisy-text score among all seven models we have measured so far.

[PARAGRAPH:gurultu_ii]
In the hardest part of our test, reading the full invoice on noisy text, none of the three models got a single invoice right across the first thirty invoices, so the test was stopped early.
The models read some of the fields partially, but they couldn't extract a complete invoice with all of its line items.
Pure software, meanwhile, managed to read only six of the two hundred invoices in this demanding test.

## ÇOKLU

[VOICE:NARRATOR] [PARAGRAPH:coklu_kur]
Next, we moved to an office's real question: what happens when multiple invoices arrive at the same time?
We kept the number of invoices processed at once at eight, and distributed that load in three different ways.
We either packed the invoices into a single request, sent them to a single agent at the same time, or distributed them across separate agents of the model.

[PARAGRAPH:coklu_sonuc]
When we packed eight invoices into a single request, accuracy collapsed in this group too.
The new version, which read one hundred sixty-one invoices accurately when given one by one, didn't produce a single valid answer this time.
That zero is an artificial number as well; packing eight invoices into a single request was our choice, and the model read those exact same invoices when we fed them one at a time.
When we ran eight separate agents of the model side by side, accuracy held steady and speed roughly doubled.
We also saw something new in this group: Qwen three kept its accuracy and more than doubled its speed even when we sent eight jobs at once to a single agent, whereas in the first group that setup hadn't sped up MiniCPM at all.

## SONUÇ

[VOICE:NARRATOR] [PARAGRAPH:sonuc]
Let's bring the results of the second group together.
On the basic-field reading task with clean text, L-F-M two point five reached eighty percent and clearly outperformed pure software.
The older version from the same family and Qwen three stayed behind pure software; part of Qwen three's loss comes from packaging and will be measured again in the custom test videos.
When we degraded the invoice, pure software faltered while the new version of the model stood firm, and the gap between them more than doubled.
On the full-invoice reading task with clean text, the best result was twelve out of two hundred invoices.
On noisy text, none of the models got a single read right across the first thirty invoices.
In the multi-invoice test, the lesson from the first group didn't change: packing multiple invoices into a single request broke accuracy, while separate agents preserved accuracy and roughly doubled the speed.
These results show the performance we got from these models in this test system, with this data, and under this workflow; they are not a verdict on the models' general capability, nor are they the final best scores we can get from them.
We will see these models again in the custom tests, where we take each model individually and push it to its limits.

## DEĞERLENDİRME

[VOICE:CLOSER] [PARAGRAPH:degerlendirme]
To me, the best part of this video was seeing the difference between two models of the exact same size on the exact same invoices.
We are often told that a bigger model is better; here, without changing the size at all, only the version changed, and the score doubled.
I also have to say this: for the first time, even on clean invoices, a model clearly beat our rule-based pure software, and it did so not just by finding more right answers, but by following instructions better.
The moment that really excited me was when we degraded the invoice; while our software faltered there, the new version of the model held its ground and gave the clearest answer yet to the question we asked in our introduction video.
I find Qwen three's case very instructive too; even when we turn thinking mode off, traces of that thinking can leak into the output, and you only spot it when you open the answers and inspect them one by one.
Full-invoice reading still sits above this weight class; yet on clean text we saw the highest full-read score so far, and that makes me think the door to this task isn't closed.
My takeaway from the multi-invoice test is the same as in the first video: giving work to a model one item at a time yields much better accuracy than dumping everything on it at once, and the fastest option is generally to hand one job each to separate agents of the model.

## SIRADAKİ VİDEO

[VOICE:NARRATOR] [PARAGRAPH:siradaki]
In the next video, the third and final group will enter the common test.
These are MiniCPM five's bigger sibling, Qwen three point five, and the Qwen three point eight distillation model trained on top of it by the community.
These three models are the largest in the common test.
In that video, using the exact same invoices, we will see whether the scores grow as the model size grows.
Do you think size alone is enough, or will version differences take the lead again?
Stay tuned.
