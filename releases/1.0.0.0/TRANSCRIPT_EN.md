# 1.0.0.0 — LLM Test Office introduction · English transcript

One sentence per line. Voices: `[VOICE:HOOK]` hook, `[VOICE:NARRATOR]` narrator, `[VOICE:CLOSER]` closing. 152 sentences; English sentence N = Turkish sentence N. Numbers and codes are spelled for the voice (e.g. 'H-N seven-three-zero-six', 'Q four').

## KANCA

[VOICE:HOOK] [PARAGRAPH:kanca]
Invoices are on our table, as our test subject.
On a clean invoice, a plain software application, one that uses no AI model, reads seven out of every ten invoices.
But when the zeros turn into capital O's and the ones into lowercase L's, it gets a full, correct read on only six of two hundred invoices.
Could a small AI model fill the gap in between?

## GİRİŞ

[VOICE:NARRATOR] [PARAGRAPH:amac]
Our aim is to look for an answer to this question: starting from the smallest models, where can we use local AI models, and how can we use them most efficiently?
To do that, we take people's own experiments into account, and we test with engines that work on real-life data, or on data produced to match real-life data, that is, data that contains errors too.
Our tests look nothing like classic benchmarks.

[PARAGRAPH:itiraf]
I'll confess: I don't know what's inside a model, or its technology, down to the finest detail, and I can't.
What I focus on is what a model can give us, and we aim to find that out through real measurements.
The process isn't made up of good news alone.
Where we ran into which error, and which fix improved which model; all of it is part of the digital archive we're trying to build.

[PARAGRAPH:cihaz]
Right now our test device is an Asus ProArt H-N seven-three-zero-six laptop.
This device, which is my own, has one hundred twenty-eight gigabytes of unified memory, and that makes it a good environment, especially for trying out several models.
The device we have is not a supercomputer, but it's not below the market average either.
For that reason, we spread our tests across other devices too; an office mini PC with only a C-P-U chip, and computers with external graphics cards, are both part of our test system.

[PARAGRAPH:gorev_adami]
Put simply, we can say that the abilities of AI models grow as the number of parameters grows.
That doesn't mean there are no lower-parameter models that give better results in certain areas.
You could describe low-parameter models as doers, and high-parameter models as both thinkers and doers.

[PARAGRAPH:kucukler]
Sometimes we put huge models to work on simple jobs when a simple model would do, losing both money and time, and most of the time we don't even realize it.
It's already well known that Claude, GPT and the rest produce excellent work.
We made it a priority to shed light on the part that's really unknown, and that's why we chose to start with small models.
There's a short video where I explain the channel itself; if you like, the link sits in the corner of the screen.

## TEST OFİSİ

[VOICE:NARRATOR] [PARAGRAPH:derlem]
First we chose the size, and set the range at one to two and a half billion parameters.
Then we listened to people.
We scanned what has been done with models of this size on GitHub, Hugging Face and Hacker News since the summer of twenty twenty-four, and we looked for answers to who achieved what, who asked what, and who tried what and gave up halfway.

[PARAGRAPH:kirk_alti]
Forty-six different tasks came out of it.
So that it could guide both us in our more advanced tests and those of our viewers who work in a particular profession, we grouped these forty-six tasks with the related ones together.
The biggest group was about office work.
Every test topic was something an administrative assistant or an accounts clerk does again and again in a day.
So we started our tests with this large group of topics.

[PARAGRAPH:test_office]
L-L-M Test Office covers twelve different tasks.
Here are the tasks we'll go through one by one in our upcoming tests, in this order.
One: pulling the date and the sender out of an email.
Two: pulling numbers and measurements out of a piece of text.
Three: pulling structured data out of the image of a document, such as an invoice.
Four: reading the text in a scanned document.
Five: answering questions about the workplace.
Six: searching among the files on a computer.
Seven: summarizing a long text.
Eight: drafting an email and summarizing an incoming email.
Nine: turning a harsh message into a polite tone.
Ten: rewriting a sentence.
Eleven: correcting grammar mistakes.
Twelve: suggesting a reply to a message.

[PARAGRAPH:neden_fatura]
We started with reading documents, and we chose the invoice as our document.
An invoice lands on every office's desk, real examples can be found online, and a small mistake while reading one can turn directly into financial loss.

[PARAGRAPH:amerika]
Since the channel's address is in America, the test parameters were set accordingly: the currency is the dollar, the date format is the American one, and the language is English.
While testing, we came across something that surprised us: in America, there's no government-mandated standard invoice format.
Because every accounting program has established its own convention, we came across invoice types that differ from one another.

[PARAGRAPH:iki_dunya]
Actually, even before the invoices in different styles, we noticed something else.
In America there were two different invoice worlds.
One was a kind that can be printed on paper for people; the other was a different kind that uses a common language only between machines.
One is written for the human eye; it has boxes, headings, and a bold total.
The other is E-D-I: plain text, marked line by line, that one machine writes for another.

## MOTOR

[VOICE:NARRATOR] [PARAGRAPH:kural_mahremiyet]
While building the common test engine, we set ourselves three rules.
First: we didn't use real data; we wrote a small engine that produces realistic data.
We changed the seller names and phone numbers every time.
The buyer name, on the other hand, we kept fixed as Test Office.

[PARAGRAPH:kural_katalog]
Second, we decided in advance which goods would be used on the invoices.
The production engine picked from thirty-four different goods, in different kinds and different quantities, and so produced a different invoice every time.

[PARAGRAPH:kural_kayit]
Third, for every invoice we generated, we set the correct answer in advance.
Had we not done that, then in evaluating the software, the model, and software plus model, we would have had to check not only the reader but the generator as well.

[PARAGRAPH:ezber]
During testing we realized that the model-free software we had written wasn't reading the test data but memorizing it, and we stepped in right away.
We moved the data around; we varied the labels for things like invoice number, date, and total, and we managed to put a stop to the memorizing.
The same piece of information now sits under a different name, in a different corner, on every invoice; examples are on screen right now.

[PARAGRAPH:kademe]
The test has two levels.
In the first, we ask the model for five pieces of information: invoice number, date, seller, tax, and total.
In the second, we ask for everything: due date, order number, discount, and all the line items, such as shipping.
These two jobs, different in difficulty, give us this prediction before testing: for the easy job, a fast, low-parameter model; for the hard job, a slow but bigger-parameter model should be preferred.
It should be remembered that here we are speaking within the limits of our test parameters.
So, do you think it turned out the way we predicted?

[PARAGRAPH:bozma]
A test run on perfectly clean data wouldn't have taught us anything.
So we produced three different scenarios in which we could read the invoice: clean text, text that's noisy as if it had passed through a scanner, and the picture of the page itself.
We didn't create the noise at random.
We swapped the look-alike characters a scanner really does mix up: zero and capital O, one and lowercase L or capital I.
We never turned one digit into a different digit.
That kind of change would have altered the test data rather than made it harder.
So we left it out of the test.

[PARAGRAPH:edi]
The generator can print the same record in four layouts: classic, compact, email, and E-D-I.
We keep E-D-I invoices in a separate lane.
So, would we have needed a model to read an invoice that one machine wrote for another?
We tested this too, and found that a plain parser reads E-D-I invoices flawlessly.
We left this invoice type, which needs no model intelligence, out of the test.

[PARAGRAPH:kusur_bir]
In the first trials, we put a question in front of every error: was the model wrong, or the engine itself?
We found four flaws.
The tax mark was stuck to the end of the product name; the models took it as part of the name, so we moved the mark into a separate column.
Because there is far more data in the contents of an invoice, we kept the noise away from the invoice numbers, and we made sure that every invoice the test engine produced was evaluated and that the result of the evaluation came back to us.

[PARAGRAPH:kusur_iki]
We hadn't specified the format at the start either; each model wrote the date its own way, and some gave the discount with a minus sign.
Now we ask for the date in year-month-day order, and for the discount as a positive number.
The last flaw was a chain: because the line items were matched in order, one single mistake meant that everything after it was counted as wrong too.
Now we look at the description first, then at the quantity and the price.
We didn't touch the flaws that came from the model; in the model-based testing process, for fairness' sake, we worked to improve the software side of the test engine, and as we said before, we didn't include the E-D-I invoice type, which needs no model, in the testing process.

[PARAGRAPH:ders]
And there's a lesson we're not hiding.
When describing the seller name, we told the model, "don't write the address, phone, or email."
The small models wrote exactly that phone number as the seller name.
We took the instruction back, and decided not to give the model a list of prohibitions.

## KANIT

[VOICE:NARRATOR] [PARAGRAPH:dondurma]
We ran the common test engine we had settled on with ten different models.
We took care that the common test engine stayed equally neutral toward every model.
Changes made for one model did not affect another model's result.
This let us see certain flaws in the models during the common test and preliminary review, and it told us that what is right for one model is wrong for another.
You'll see how we handle all of this data later, in the model-specific custom test process.

[PARAGRAPH:taban]
Alongside every test, we also ran pure software that uses no model at all.
On clean invoices it read seven out of every ten; once noise came in, it managed a full read on only six of two hundred.
Here we found this: on clean documents, pure software is much faster and cheaper.
On the contrary, on noisy text, model intelligence steps into exactly the rescuer role we were looking for.
That's why noisy text is the main material of our tests.

[PARAGRAPH:gercek_hayat]
We deliberately kept custom documents, and real-life data, out of the common test.
Because at the start we didn't know which model wanted software support in which respects, or which topics it was good at.
We obtained much of this information through the common test.
The custom tests we'll start once the common test videos are finished give each model the best software support, and make the control data as noisy and as hard to read as possible.
With these custom tests we ran things under harder conditions, not to get artificially positive results, but to get an answer to the question of whether we can use a model in a real working environment.

[PARAGRAPH:modeller]
The list of models we put through the test, in increasing order of parameter count, is as follows.
Gemma three, one billion.
MiniCPM five, one billion.
L-F-M two and L-F-M two point five.
Llama three point two.
SmolLM two.
Qwen three point five.
Qwen three point eight.
Qwen three.
And last, MiniCPM five at two and a half billion parameters.

[PARAGRAPH:hukum]
Getting a negative result from a model won't amount to a verdict on its general ability; it will only show the performance we got from it in this test system, with this data, and this way of working.
In the common test, every model entered with the Q four quantization setting.
While testing the models, we're also testing the most efficient way and conditions to run them.
If a model runs efficiently in its Q four version, we thought there's no need to prefer Q eight and lose speed; tests of Q eight, and for some models even the F sixteen versions, take place in the custom tests.

## ÖLÇÜM

[VOICE:NARRATOR] [PARAGRAPH:dogruluk]
We measure three things.
The first is accuracy; our scoring here is strict: an invoice passes only if all of its information is correct and the answer comes in exactly the requested format.
If the answer is correct but wrapped between code markers, the strict score doesn't let it pass; so as not to lose it, we keep a flexible score alongside.
The gap between the two shows not that the model couldn't read, but that it couldn't package the answer; closing that gap is the job of the custom test.

[PARAGRAPH:hiz]
The second is speed: we measure how many seconds it takes to read one invoice and how many invoices come out in a minute.
The third is an office's real question: what happens when more than one job arrives at the same time?
First we run the single test: one model, one request, one invoice.
Then we raise the number of invoices in flight at the same time to eight.
We spread the load in different ways: to separate copies of the model, to eight requests arriving at a single copy, or to eight invoices inside a single request.
Which one speeds things up and which one keeps accuracy intact, we show in the common test videos.

[PARAGRAPH:yol]
The video series we're introducing will move forward through these stages: the common test process, evaluation of the common test process, the custom test process, evaluation of the custom test process, and the ranking of models.
After that, once we've identified which model works efficiently on which job, comes the writing, using, and reviewing of an application that can be used in real life.

[PARAGRAPH:arsiv]
We keep every test, every result, and the model files themselves as they were on the day of the test.
We seal the results with a timestamp and a digital signature; if anything changes afterward, even if we are the ones who changed it, it's immediately noticed.
Because models are constantly being updated, and when we run the same test tomorrow on a new model, we want to state the difference between yesterday and today not by guessing but with the same yardstick.
The fingerprints of the seals are in the video description.

## TOPARLAMA

[VOICE:CLOSER] [PARAGRAPH:toparla]
Let's go back to the beginning.
There was an invoice on the table and a question: can a small model fill the gap in between?
On clean paper a simple program gets most of the job done; once the paper gets degraded, it stumbles.
The value of small models is sought in exactly that gap; we show it not by assuming but by measuring.
The common test engine is built, its flaws are weeded out, and it's frozen.
The common test engine is complete; now the invoice samples are on the table, and it's the models' turn!

## SIRADAKİ VİDEO

[VOICE:HOOK] [PARAGRAPH:siradaki]
In our next video, we start the common tests.
First in line are MiniCPM five and Gemma three.
Then comes Llama three point two.
Then SmolLM two.
Stay tuned for the result of the two-hundred-invoice common test.
