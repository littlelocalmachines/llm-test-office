# 1.1.1.0-1 — LFM3 1.7B interim video · English transcript

One sentence per line. Voices: `[VOICE:HOOK]` hook, `[VOICE:NARRATOR]` narrator. 74 sentences in 17 paragraphs; English sentence N = Turkish sentence N. Letters and versions are spelled for the voice (e.g. 'L-F-M three', 'Q four K M'). This is the text that was voiced in the video.


## HOOK

[VOICE:HOOK] [PARAGRAPH:kanca]
On top of the two hundred invoices on our desk, three versions of the same family are written down.
The first version had read seventy-seven of the two hundred invoices correctly.
The middle version jumped to one hundred sixty-one.
So can the family's new model become a candidate for our document-reading work without any software support?

## BODY

[VOICE:NARRATOR] [PARAGRAPH:aday]
The newest member of the family is now sitting on our desk.
Liquid A-I released its new model on October twenty-third, twenty twenty-six.
It's called L-F-M three, and it has one point seven billion parameters.
This family more than doubled its correct count in a single version, and we wanted to see what it did with its next step.

[PARAGRAPH:surec]
Our goal isn't to make models race; it's to see whether this model can become a candidate for the document-reading work of the L-L-M Test Office.
To do that, we put L-F-M three through the common test, where every model gets the same prompt and the same rules.
In the common test, the model reads on its own, with no support at all.
Then, in the custom tests, software, character recognition, and vision-model support are added one at a time.
At the end of the process, we record which kind of support each candidate needed to finish the job, and how much memory that took.
We're comparing the new candidate at the same table with the seven models whose results we've published so far.

[PARAGRAPH:kimlik]
The model's identity is recorded in the lines of its model card.
I'll admit it: I don't know its internal architecture in detail; we're taking the structural information straight from the model card.
The card lists a twenty-four-layer design that combines short convolution and attention layers, and a license that allows commercial use below a certain revenue limit.
For our measurements we used the Q four K M quantized file, and we verified that the file we downloaded matches the checksum published on Hugging Face exactly.
As with the previous models, we ran our tests on English invoices.

[PARAGRAPH:duzen]
Our measurement setup is the same as in the previous tests.
To keep the comparison fair, we put on the desk the same two hundred synthetic English invoices that the previous models had read; that way, any difference between two models comes from the model itself, not from the invoices.

[PARAGRAPH:kademe]
We split the test into two levels.
In the easy test, we ask for five basic pieces of information from the invoice: the number, the date, the seller, the tax, and the total.
We also ask the model to convert the date into a specific format, in year, month, and day order.
In the hard test, we ask for the whole invoice, line items included; alongside details like the due date, subtotal, discount, and shipping, that also covers each line's description, quantity, and amount.

[PARAGRAPH:puanlama]
We use two different scoring systems.
The first is the strict system: we want the right answer in a specific shape, and if even one of the requested details is wrong, the invoice fails.
This condition is necessary for an application that uses the model to run without problems.
The second is the flexible system: we don't hold the model to the shape, and only check whether the content is correct.
The gap between the two systems shows how much software support the model needs.

[PARAGRAPH:taban]
We also ran a no-model program as a baseline: written with rules, using no A-I.
When we compare two models, we use a statistical test that puts their results on the same invoices side by side.
This test gives the probability that the difference between them could be explained by chance; if that probability isn't below five percent, we don't call either model better or worse.

[PARAGRAPH:kolay]
In the easy test, the results came out close to the family's previous version.
The new model reads one hundred fifty-six of the two hundred invoices correctly.
Across from it sits the family's previous version, L-F-M two point five.
That version had scored one hundred sixty-one correct on the same test.
The difference is small enough to be explained by chance; it wasn't significant in the statistical test.
So we call the new version neither better nor worse.

[PARAGRAPH:kolay_taban]
The no-model program reached one hundred forty-two correct on the same deck.
The new model doesn't differ significantly from this program in the statistical test either.
It may look second in the ranking alongside the seven models whose results we've published, but since there's no significant difference between close numbers, this position doesn't count as a verdict of superiority.
In the flexible system, the result didn't change either, and stayed at one hundred fifty-six.
When we sent the invoices in different formats within the same run, the result still stayed between one hundred fifty-six and one hundred fifty-seven.

[PARAGRAPH:zor]
In the hard test, where we ask for the whole invoice, the results are very different.
The new model read eighty-five of the two hundred invoices completely; the result is the same in the flexible system.
The previous version, L-F-M two point five, had scored the highest number in the easy test, but it falls far behind in the hard test.
That version could read twelve invoices completely, while the first version couldn't read a single invoice completely.
None of the seven models whose results we've published had gone above twelve on this test.

[PARAGRAPH:zor_sinama]
We checked this gap with the same statistical test as well; the difference is too large to be explained by chance.
But let's note that we added this test after seeing the results.
That's why we present it not as a firm verdict, but as a notable finding.

[PARAGRAPH:kayip]
An interesting pattern emerged from the losses in the easy test.
In thirty-six of the forty-four invoices it missed, the answer contains an extra field we didn't ask for.
We had seen this category in the first version too.
That model had written extra information we didn't ask for on twenty-five invoices.
The middle version never did this; all thirty-nine invoices it lost are wrong-value errors.

[PARAGRAPH:kutuk]
This log doesn't hold a single reading, but answers in which the same invoices were read again and again in different layouts.
To see what these extra fields were, we examined the four hundred twenty-nine header answers left in the server log.
The same behavior repeats in seventy-nine of those records.
The model left the raw date from the document in the date field, and wrote the requested year, month, and day format into a second field it named itself.
In all seventy-nine of those answers, the conversion in the second field was correct.
In other words, the model reads the date correctly, but turns the conversion instruction into a new field name.
The flexible system doesn't rescue these invoices either, because the date in the requested field isn't in the requested format.
Because the log rotates and doesn't map one-to-one to the losses in the main run, this count only reflects the records we have.

[PARAGRAPH:sinirlar]
Before reaching a verdict, let's note the limits at the edge of the desk.
We ran the trial only once; since the computer's power plan differed from our earlier measurements, we're not comparing speed.
Keep in mind that the statistical test on the hard test was added afterward, and that the log count is only partial.
Since the no-model program was written by someone who knows the software that generated the invoices, our baseline is optimistic; and this test doesn't measure results on real documents.

[PARAGRAPH:kapanis]
For L-F-M three, the common test process is complete.
If you came across a model that converts the date correctly but writes it into a second field it opened itself, where would you take the first step: would you change the prompt, or would you clean up that field with a small piece of software?

[PARAGRAPH:sonraki]
For now, our last contestants in the common test process are MiniCPM five, Qwen three point five, and Qwen three point eight distill.
We'll keep making interim videos for new models released along the way.
The next video goes live on Thursday, November twelfth, at five p.m. New York time.
