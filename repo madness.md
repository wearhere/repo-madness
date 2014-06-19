<!--
Repo Madness: Taming the Teenage Open-Source Repository (c) by Jeffrey Wear

Repo Madness: Taming the Teenage Open-Source Repository is licensed under a
Creative Commons Attribution-ShareAlike 4.0 International License with the
following caveat:

This presentation may contain images owned by others. Where possible citations
for the images are provided (in the form of hypertext links to the source Web site).

You should have received a copy of the license along with this
work. If not, see <http://creativecommons.org/licenses/by-sa/4.0/>. 
-->

# Prelude

---

<!-- Subliminal logo -->
![100%](http://f.cl.ly/items/1l0R1h1Z0k0r1y1X440y/Subliminal.png)

^ A year ago, I and my coworkers at Inkling released an iOS integration testing
framework called Subliminal.

---

```objc
- (void)testLogInSucceedsWithUsernameAndPassword {
    NSString *username = @"Jeff", *password = @"foo";
    [_usernameField setText:username];
    [_passwordField setText:password];
    
    [_submitButton tap];

    SLAssertTrueWithTimeout([_loginSpinner isInvalidOrInvisible], 3,
    						@"Log-in was not successful.");
    
    NSString *successMessage = [NSString stringWithFormat:@"Hello, %@!", username];
    SLAssertTrue([[SLElement elementWithAccessibilityLabel:successMessage] isValid],
    			 @"Log-in did not succeed.");
}
```

^ Integration tests exercise the application's UI. Here's what a Subliminal test
case looks like.

---

<!-- Above test case running -->
![](http://cl.ly/0H2D063I1p2h/download/Subliminal%20Test.mov)

^ When you run the test, you can see that Subliminal enters the username and
password into the text fields, then presses the login button. Meanwhile,
Instruments shows the progress of the test.

---

- Objective-C tests
- No private APIs
- No dependencies
- Fully-tested

^ Here are some features of Subliminal. These features make it something of a
rarity among integration testing frameworks. But testing is a hard sell.

---

# __*AFNetworking*__ lets you __communicate with other machines__ so you can __download images__.

^ As example, look at AFNetworking. The capability is interesting, but the
application makes it desirable. And the applications of networking are well-known
--so well-known that AFNetworking can implement many of them for you.

---

# __*Subliminal*__ lets you __manipulate your UI and make assertions__ so you can __???__.

^ With Subliminal, the application--what to test, _why_ to test--is left to the user.
It's a hard sell.

^ Moreover, Inkling is not a big company. We only have (at the time of writing,
06.11.2014) about 100 employees, with only 3 full-time iOS engineers, myself
included.

---

- 491 stars

^ Nevertheless. For comparison, this is a fifth of what KIF has.

- 45 watchers
- 13 contributors

^ I'd like to think that some of this is due to the care that I and my 
collaborators have put into the repo, and the outreach that we have done.

^ This is the story of how we learned to do those things.

---

# REPO MADNESS

<!-- _Reefer Madness_ screen cap -->
![fill](http://publicdomainreview.org/files/2011/08/reefer-madness.jpg)

---

# [fit] http://nshipster.com/stewardship/

> Earlier this year, Mattt Thompson wrote an essay on open-source stewardship:
on launching an open-source project with your eyes open to the responsibilities
that lie ahead.

---

> It's not enough to dump a pile of source code somewhere and declare it "open source".
-- Mattt Thompson

^ "The first step of stewardship is to establish clear expectations."

---

<!-- _What to Expect When You're Expecting_ -->
![left](http://media.npr.org/assets/bakertaylor/covers/w/what-to-expect-when-youre-expecting/9780761148579_custom-a68e944e3bb3da38b68fa9cc0b426c2fd8a7461a-s6-c30.jpg)

✓ README
✓ LICENSE
✓ Cocoapods

^ Mattt talked about several must-haves _before_ you launch your repo, but he
didn't talk much about what happened after that.

---

# And then?

^ Well, with a bit of luck, and if your repo solves a problem....

---

<!-- Miley as a smiling kid -->
![](http://www.heatworld.com/images/121542_615x2000_STD/2013/9/Images/Gallery/3miley.jpg)

^ Your users will grow...

---

<!-- Miley unsmiling -->
![](http://www.nicewalpaper.com/wallpapers/miley-cyrus-hannah-montana-1-nice-wallpaper-1600x1200.jpg)

^ Your README will grow...

---

<!-- Edgy Miley pouting -->
![](http://3.bp.blogspot.com/_kiPHvAIjxso/R5IAK8azVFI/AAAAAAAAFq0/U136g7ICkgM/s1600/cyrus%2Bmiley%2B2008%2Bjan%2Bsilver1.jpg)

^ Your number of issues will grow...

---

<!-- Miley with shaved head in leather jacket -->
![](http://i2.dailyrecord.co.uk/incoming/article1949596.ece/alternates/s2197/Singer-Miley-Cyrus-attends-the-new-Myspace-launch-event-at-the-El-Rey-Theatre-on-June-12-2013-in-Los-Angeles-California.png)

^ Your number of pull requests will grow... and you start thinking to yourself,
my project's gotten kind of serious. Kind of scary. My little project might be...

---

<!-- Miley tongue Google search -->
![](http://f.cl.ly/items/2r1E0U2k1W3X0s341U36/Screen%20Shot%202014-06-10%20at%2010.24.31%20PM.png)

^ ...a teenager!

---

# Hold on.

^ You say: My project is normal, it's healthy, it's just a little...

---

<!-- Shaggy teenage Zac Efron -->
![](http://images.j-14.com/uploads/photos/file/12422/zac-efron-awkward-teenager.jpg?crop=top&fit=clip&h=500&w=698)

^ Awkward. Well ok. Well ok! Because _this_...

---

<!-- Shaggy teenage Zac -->
<!-- Well-groomed Zac -->
![](http://images.j-14.com/uploads/photos/file/12422/zac-efron-awkward-teenager.jpg?crop=top&fit=clip&h=500&w=698)
![](http://f.cl.ly/items/3w0q1b2I2E0D3a2d150I/cached.jpeg)

^ ...is fixable. Maybe not the hair... I could go either way on the shirt...
but Zac's teeth are perfect. How do you do that?

---

<!-- Braces -->
![](http://www.clarendondentalspa.co.uk/assets/images/default/radiance_clear_braces_leeds_orthodontists_clarendon_dental_spa.png)

^ You get braces!

^ Now some of you are thinking, that's a cure worse than the disease. But...

---

<!-- Braces -->
![](http://www.clarendondentalspa.co.uk/assets/images/default/radiance_clear_braces_leeds_orthodontists_clarendon_dental_spa.png)

# Braces keep _existing_ growth on track.

^ Your project's going to grow whether you like it or not--the question is,
how are you going to support that growth? Also...

---

<!-- Braces -->
![](http://www.clarendondentalspa.co.uk/assets/images/default/radiance_clear_braces_leeds_orthodontists_clarendon_dental_spa.png)

# Braces support _new_ growth.

---

<!-- Scaffolding on Golden Gate Bridge -->
![](http://cdn-3-service.phanfare.com/images/external/5025354_4977318_135486119_WebLarge_2/0_0_5395a5973512fae5ed19fc26676c2d93_1)

^ Think of braces as scaffolding...

---

<!-- Golden Gate Bridge -->
![](http://upload.wikimedia.org/wikipedia/commons/0/0c/GoldenGateBridge-001.jpg)

^ ...some projects couldn't be built without it.

^ But even if your project doesn't have such grandiose ambitions,
you should still get braces.

---

<!-- "HAS A YEARBOOK PICTURE... GETS BRACES THE DAY BEFORE IT" reaction pic -->
![inline](http://www.quickmeme.com/img/69/69327a70fa9f6baf0561e74e395325713ae54d13e1d2aaa996ceaff96e61c78d.jpg)

^ You don't want to be caught needing braces.

---

# Braces for projects.

^ Now that I've talked about why you need braces, and who should get braces,
let's talk about what braces look like in the context of an open-source project.
Remember that braces support growth.

---

# Braces support growth in...

- documentation
- user support
- development

^ As a project grows, its documentation grows, its user support needs grow,
and of course its development needs grow. Let's apply braces to each of these areas.

---

# Braces for documentation.

---

<!-- XKCD on university websites -->
![inline](http://imgs.xkcd.com/comics/university_website.png)

^ I'm sure you've all seen the famous XKCD comic about university websites
--about the disparity between what people go to the site looking for, and
what's _actually_ on the site.

^ I'm afraid to say that your project's README is kinda similar.

---

<!-- Things in your README vs. things people go to the README looking for -->
![inline](http://f.cl.ly/items/233a0z0C0W3q2t2O3X2X/README%20vs%20READFIRST.png)

^ Maybe not quite as bad: the things that people go to your README looking for
are probably a subset of the things actually in your README. But your README still
has a lot of extraneous stuff.

^ But, you say, all these things are important! Yes, but they're not _equally_ important.

---

<!-- README, as read by maintainer -->
![](http://f.cl.ly/items/362r1G1v1a3x2J1V1O1Q/readme%20layout.001.jpg)

^ This diagram shows the components of a typical README. These are actually Mattt's
suggestions from the essay I mentioned earlier.

^ And this is probably how they're laid out, in the order you the maintainer
thought was interesting. After the introduction, you wanted to talk about your features,
then obviously installation, then the boring stuff like the LICENSE at the end.

^ And you read straight down.

---

<!-- README, as read by maintainer vs. new user -->
![](http://f.cl.ly/items/0B1w3o1b2k3p2s1q342H/readme%20layout.002.jpg)

^ New users will read this a different way. After finding out what your project is,
they've got to figure out if they _can_ use it before they think about usage.
Then they've got to think about installing it before using it.

^ And this is ok as long as your README is pretty small--it's easy to take it all in
either way.

---

<!-- Expanded README -->
![](http://f.cl.ly/items/1i17413E3f312W18043F/readme%20layout.003.jpg)

^ But when you start adding new features and fleshing out your installation instructions,
you're making it less approachable for new users.

^ The solution: take stuff out!

---

# [fit] README
# [fit] READ FIRST

^ README is a misnomer. It's only _one_ part, the _first_ part, of your project's
documentation.

---

<!-- Usage section of README  -->
![fit](http://f.cl.ly/items/3o1X0e1P3B3E3V042o0j/Screen%20Shot%202014-06-11%20at%203.23.04%20PM.png)

^ Your README doesn't need to describe how to use your project in-depth.
It just needs to give a flavor.

---

<!-- Installation section of README  -->
![fit](http://f.cl.ly/items/0E0p1n1b2H0J3P1q1b45/Screen%20Shot%202014-06-11%20at%203.26.16%20PM.png)

^ Your README doesn't even need to describe how to install your project.
It just needs to tell people where they can find that information.

^ And where should you point them?

---

<!-- Wiki on front page of repo -->
![](http://f.cl.ly/items/1G1F182f1W3O3d1h0y3L/wiki.png)

^ The wiki! Wikis used to be kind of like projects' attics, but GitHub revamped
them just last month.

---

<!-- Wiki home page  -->
![](http://f.cl.ly/items/430u111R351w0j0q0H3k/Screen%20Shot%202014-06-11%20at%203.52.08%20PM.png)

^ Now they have access to the same nice formatting as your README. But the wiki scales.

^ Check out this nice sidebar on the right.

---

<!-- Instructions with lots of screenshots  -->
![autoplay](http://cl.ly/2K3X0V2p1o2D/full%20instructions.mov)

^ You can put instructions with tons of screenshots on the wiki. If the README
was this detailed it would be pages long!

^ And Subliminal's README used to be that way. Other projects' still are.

---

# Braces for user support.

^ No matter how good your documentation is, your users will want to contact you.

---

<!-- Jodie Foster listening to satellite dishes  -->
![](http://www.podcastfilmreview.com/wp-content/uploads/2011/04/Contact22.png)

^ They shouldn't have to search for a way to do so.
But it's not immediately clear what you should offer them. An email? A Twitter account?

---

<!-- Tweet to @subliminaltest  -->
![](http://f.cl.ly/items/0x1I2H3Q2f1h0i3Z293h/Screen%20Shot%202014-06-11%20at%204.39.04%20PM.png)

^ You can fit about two lines of Objective-C in a tweet.
Twitter's not great for technical support.

---

<!-- Issues on front page of repo  -->
![](http://f.cl.ly/items/3g2h3B2y031x2F0E1T20/Issues%20position.png)

^ Without a good solution, your users will reach for the option right in front
of them: GitHub issues.

---

<!-- Issue list  -->
![](http://f.cl.ly/items/1k3j3J1c3x001o26330t/issues%20list.png)

^ Issues should be for development. And if you look at Subliminal's list,
most of them are that way. But this one issue got through.

^ At first, it looked like it might point out a flaw in our documentation.
But it turned out that the user had just misread something. And then, as long
as he had me "on the line," so to speak, he started to ask unrelated questions.
And then he never got back to me--so I don't know whether he still needs help or not!
And so this issue just sits there sadly.

---

<!-- Issue tags -->
![](http://f.cl.ly/items/2o0E280d2d313K0f060q/tags.png)

^ I think that it's not immediately clear what GitHub issues ought to be used for.
GitHub doesn't help matters. One of their default tags is "question".
What does that mean?

^ "What is an issue?" should never be a question.

---

- If you **need help**, use [Stack Overflow](http://stackoverflow.com/questions/tagged/subliminal). (Tag 'subliminal'.)
- If you'd like to **ask a general question**, use [Stack Overflow](http://stackoverflow.com/questions/tagged/subliminal).
- If you've **found a bug**, [open an issue](https://github.com/inkling/Subliminal/issues/new).
- If you **have a feature request**, [open an issue](https://github.com/inkling/Subliminal/issues/new).

^ Subliminal tells users where they should contact us--in different places
depending on their needs. Issues are for development--not questions.

---

## Stack Overflow is the best place for questions.

^ Your project isn't "too small" for SO.

---

<!-- Tagged questions on SO -->
![](http://f.cl.ly/items/3O0O3y2g333E2h022845/Screen%20Shot%202014-06-11%20at%205.05.49%20PM.png)

^ A tag allows you to filter your questions.

---

<!-- Community answers on a SO question -->
![](http://f.cl.ly/items/2V3I272g0Q3N1E46341U/Screen%20Shot%202014-06-11%20at%205.07.21%20PM.png)

^ Stack Overflow incentivizes community participation. It rarely happens that
other people jump in to help on GitHub issues. The maintainer "owns" that space.

^ But on Stack Overflow, here's some random user helping install Subliminal using
Cocoapods--before Subliminal even had official Cocoapods support! We're equals
on Stack Overflow.

^ And support can get lost in GitHub issues. But SO questions are living. After
we did add Cocoapods support, someone else went back here and wrote a better answer.
And that rose to the top.

---

<!-- GitHub issue count -->
<!-- SO question count -->
![100%](http://f.cl.ly/items/2C2W2r261a0t0Q3L3x2J/Screen%20Shot%202014-06-11%20at%205.09.06%20PM.png)
![100%](http://f.cl.ly/items/3s2i3U2Y3r1r1n1S2L1F/Screen%20Shot%202014-06-11%20at%205.09.32%20PM.png)

^ I'd even say that Stack Overflow activity feels positive, while GitHub activity
feels kinda negative. Issues are _problems_--there's an exclamation mark! But
questions are people using your project.

---

## Get better issues with contributing guidelines.

^ While the best issue is no issue, you can get better issues.

---

<!-- Contributing guidelines -->
![](http://f.cl.ly/items/0X1r1C310r123I2o3y43/Screen%20Shot%202014-06-11%20at%205.18.59%20PM.png)

^ Put a file called CONTRIBUTING in the root of your project. Describe what you
want out of issues in that file.

---

<!-- Link to contributing guidelines above new issue -->
![](http://f.cl.ly/items/1f020q1A2s231G3J3H3r/Screen%20Shot%202014-06-11%20at%205.37.49%20PM.png)

^ When a user goes to open a new issue, they'll see a link to those guidelines
at the top.

---

# Braces for development.

^ Now that your issues are actionable, let's talk about development.
^ I bet you imagine that at this point in the talk I'm going to reveal some trick
for doing more work, faster.

^ That's not the point. Your best investment is not writing code.

---

# [fit] _Many hands_
# [fit] lighten the load.

^ You can get the most done if you don't try to do it yourself.
Take the time to support contributors, beginning with onboarding.

---

# In the contributing guidelines:

- How to set up development
- How to make changes
- How to document changes
- How to _test_ changes

^ Outline what you expect of them in the contributing guidelines. Don't expect
that they have any background in open-source--just link to GitHub's help.

---

# http://nshipster.com/unit-testing/

^ Add tests if you don't have them. Tests are how you enforce your expectations.
A full description of testing is out of scope for this talk, but I refer you
to Mattt's intro at NSHipster.

---

# Automated testing: as easy as

```sh
language: objective-c
xcode_project: MyNewProject.xcodeproj
xcode_scheme: MyNewProjectTests
```

^ Even better than testing is automated testing. By putting the above
in a file in the root of your repo...

---

<!-- "Tests passed" above merge button -->
![inline](http://f.cl.ly/items/3J0V3Y2n0Y1r2p3d2r3r/Screen%20Shot%202014-06-11%20at%206.11.11%20PM.png)

^ ...you can get a service called Travis to run your tests against every pull request.

^ We've set expectations in the contributing guidelines, we've enforced those expectations through tests,
we're good to start accepting pull requests, right?

^ Bug fixes, absolutely. But feature requests...

---

# [fit] Feature requests are
# [fit] too late.

^ Your users had a problem, and now they're committed to a solution.
Maybe that solution wasn't the easiest way to go about it, or maybe it's
a bit too narrow to address a general use case.

^ But now there's sunk costs, and feelings on the line.

---

# [fit] Separate problem
# [fit] from solution.

^ Try to recognize what your contributors are trying to do,
separate from how they've done it. But this is hard when you've
got code in front of you rather than a description of the problem.

^ Ideally, every feature would begin with a discussion--an exploratory issue;
a heads-up over Twitter or in our chat room--to establish a need for the feature,
and roughly sketch ought how best it might be solved, before investing time coding.

^ I don't want to make that a hard rule, but it would save a lot of time on everyone's part.

---

# [fit] Optimize for issues closed,
# [fit] not PRs merged.

^ Your goal should be to address users' needs with the least amount of code
possible. When you accept a pull request, you're committing to maintaining that code.

---

# [fit] Communicate.

^ Communicate with your collaborators early and often. If a GitHub thread threatens
to become overwhelming, jump "offline". Use Google Hangouts. Use Gitter. Meet
your contributors in person, if possible.

^ Recognize your common goals.

---

# [fit] Say thanks.

^ And say thanks every chance you get. Every time that someone touches your project,
whether it's to submit code or bug reports, it's a marvelous, serendipitous event.
Show them that you appreciate their time.

^ Thanks to all our contributors and users. And thanks to Inkling for making this
possible.

^ I hope that this story helps you all be better open-source "parents". Thanks everyone.

---

<!-- Perfect smile  -->
![](http://cabalinandds.com/wp-content/uploads/2013/05/Fotolia_46469499_Subscription_Monthly_XXL.jpg)

---

# Links

- http://nshipster.com/stewardship/
- https://github.com/blog/1828-wikis-now-with-more-love
- http://stackoverflow.com/help/privileges/create-tags
- https://github.com/blog/1184-contributing-guidelines
- https://github.com/inkling/Subliminal/blob/master/CONTRIBUTING.md

---

# Links con't.

- http://docs.travis-ci.com/user/languages/objective-c/
- https://github.com/inkling/Subliminal/wiki/Continuous-Integration
- https://gitter.im/

^ Slides are online here: http://cl.ly/1a2P1r3b270e.
