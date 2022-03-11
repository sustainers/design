Contributing to the Sustain OSS Design Inventory
================================================

Thanks for your interest in working on the Sustain OSS Design Inventory!
We appreciate your interest and enthusiasm.
This document explains the contribution process, the different components of the project, and how to create a development environment to work on the site.


**Table of contents**:

1. [Contribution process](#process)
1. [Structure and components](#components)
1. [How to create a development environment](#dev-env)


## <a id="process"></a>Contribution process

The Sustain OSS Design Inventory is governed by the [Sustain OSS Design & UX Working Group](https://sustainoss.org/working-groups/design-and-ux/).
The Working Group is part of the [Sustain OSS community](https://sustainoss.org/about/).
Decisions about the project, the content published herein, and other aspects are generally headed up by these fine folks (in alphabetical order):

1. Eriol Fox
1. Georgia Bullen
1. Justin W. Flory
1. Memo Esparza
1. Richard Littauer

Since the team is small and our efforts are still getting started, the governance of this project is fluid and may change over time to help us grow and scale the effort, as needed.

### Governance model: Lazy consensus

When reviewing changes or new ideas to this project, the maintainers will adhere to a **lazy consensus** model of decision-making.

**What does lazy consensus mean?**
In order for a change or new effort to move forward, it must receive _at least one_ "+1" vote from a maintainer, and no "-1" votes from any maintainer.
This enables work to move forward quickly if there are no major disagreements.
For minor and non-controversial changes, a single approval allows a change to move forward with little resistance.
If there is a change or new idea a core maintainer raises issue with, the "-1" vote requires the process to pause and have a longer discussion around a change or new idea.

**What constitutes a vote?**
In the context of this repository, a vote can mean a review on a Pull Request or a comment on an Issue.
A maintainer can give a "+1" vote or approve a Pull Request if they agree with the change.
A maintainer can also abstain on a decision by giving a "+0" vote, which will not give the required approval to make a change but neither will it block the change from moving forward if another maintainer agrees.
Finally, a maintainer can give a "-1" vote or request changes on a Pull Request if they take issue with a change and wish to either see changes made or have a longer discussion first.

**How does someone become a core maintainer?**
It is a good question.
Our effort is still very new, and we haven't worked out this question yet.
But if you have thoughts, we'd love to hear them in the `#open-design-discussions` channel in the [Open Collective Slack](https://join.slack.com/t/opencollective/shared_invite/zt-f43qko76-sD8G~e_vQCm4TtpIsM4i~A).


## <a id="components"></a>Structure and components

The Sustain OSS Design Inventory includes two components: the content (hosted in this repository) and the theme (used in building this site, but hosted separately).

### Content

The content you find published in the [public website](https://sustainers.github.io/design) is hosted here.
You can find all the content in the [`content/` directory](/content/) of this repository.
For changes to content, categories, and the text published on the website, this repository is the place to have discussions, submit changes, and collaborate with the Design & UX Working Group.

### Theme

The website theme that provides the interface and UX of the public website is the [UNICEF Inventory theme](https://github.com/unicef/inventory-hugo-theme).
It is a theme made for the [Hugo static site generator](https://gohugo.io/).
For changes to the site look-and-feel, user interface, and user experience, you can open bug reports, feature requests, and ideas in the [issue tracker](https://github.com/unicef/inventory-hugo-theme/issues) of the UNICEF Inventory theme.


## <a id="dev-env"></a>How to create a development environment

So, you want to work on the Sustain OSS Design Inventory?
Great!
This section describes how to set up a development environment using Hugo.
A development environment is needed to test changes and build the site locally.
While it is helpful for reviewing changes, it is not required so long as the continuous integration pipeline is passing on a Pull Request.

### Requirements

To create a developer environment, you need to have the following:

* [Hugo](https://gohugo.io/getting-started/installing/)
* [git](https://github.com/git-guides/install-git) or a git client

### Setting up the environment

The Design Inventory actually has _two_ git repositories combined into one.
This is done with [git submodules]().
To build the site locally, you need to clone the [`sustainoss/design` repo]() with the [`unicef/inventory-hugo-theme` submodule]().

**First-time clone**:
If you have not cloned the repo yet, do it with this command:

```sh
git clone --recurse-submodules git@github.com:sustainers/design.git
```

**Add the git submodule after cloning**:
Already cloned the repo, but forgot to clone it with the submodule?
No worries.
Follow these steps to add it after.

```sh
cd /path/to/repo/
git submodule update --init
```

### Run the Hugo server

Finally, you will use Hugo to run a local HTTP web server and generate a preview of the site from your own machine.
Simply change directories to the repository, and run the Hugo server:

```sh
cd /path/to/repo/
hugo serve
```

The terminal will print a message with a URL to the local preview, such as [localhost:1313/design/](http://localhost:1313/design/).
Direct your browser to the local preview, and it should appear just as it does on the public website.
