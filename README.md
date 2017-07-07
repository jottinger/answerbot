# answerbot
A chatbot designed to present knowledge

Right now, ##java has [javabot](http://github.com/evanchooly/javabot), an excellent infobot, but one 
whose matching is largely literal. It has some replacement capability (one can set up factoids as
"`foo $1`" and it will do pattern replacement for `$1`), which is really nice... but the factoids
are still "all or nothing."

What if a chatbot were to match information *types*?

For example, I might have a set of types of questions about a topic that would make sense to manage:

1. Where is DropWizard?
1. What is DropWizard?

If someone were to inquire with a simple "`Dropwizard?`", that might by a simple "what is" question. If they 
added more information to the query, like "`Dropwizard url?`" then that would be classified as a "where is"
interrogative.

So my thought is to have a bot that applied two algorithms to each input: one to determine subject, and the
other to determine the nature of the question *if* a subject can be reliably determined.

"`Dropwizard`" might be a subject about which the bot knows - it would do matching on subjects with
high confidence only (i.e., if it's not highly confident that it knows something about DropWizard, it 
wouldn't match on subject.)

Then, if it has a subject, it would match on the *type* of query, with "what" having more priority than
"where", because "what" is probably more commonly asked. It would then respond according to an answer template.

The key, though, is how to train the system well. I'm still thinking about that.
