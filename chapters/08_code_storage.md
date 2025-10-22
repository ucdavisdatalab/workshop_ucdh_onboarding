# Code Storage and Sharing
If you care about creating code that will be usable by collaborators or your future self, then you should be using [git](https://git-scm.org) for version control and code management. A git repository can contain the entire history of development for a code project, as well as information about the reasons for changes and the ability to move back and forth through the project's history. The Datalab has a [workshop to teach users the basics of version control with git](https://ucdavisdatalab.github.io/workshop_reproducible_research/chapters/version-control/01_version-control-systems.html). Start there if you are new to version control.

While having a project history is great, the greatest benefits of git for version control come when you couple it with a collaborative service like Gitlab, which lets you share your code with a selected team of people. The benefits of version control are multiplied when you work in a team because git integrates changes and messages from team members in a controllable way. And Gitlab provides features like issue tracking that allow a team to discuss and collaborate on code changes as they work toward a goal, like fixing a bug or creating a new analysis.

:::Warning
You should never put data onto a Gitlab repository! Handling data files slows down the version tracking and even if you delete data from the current version of the repository, it remains in the project history where it is easy to forget about and later share inadvertently.
:::

There is a [private Gitlab hosted on UCDH premises](https://gitlab.ri.ucdavis.edu) that you should use for projects that might handle any sensitive code or data.