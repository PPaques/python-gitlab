##########
Iterations
##########

Project Iterations
==================

Reference
---------

* v4 API:

  + :class:`gitlab.v4.objects.ProjectIteration`
  + :class:`gitlab.v4.objects.ProjectIterationManager`
  + :attr:`gitlab.v4.objects.Project.iterations`

  + :class:`gitlab.v4.objects.GroupIteration`
  + :class:`gitlab.v4.objects.GroupIterationManager`
  + :attr:`gitlab.v4.objects.Group.iterations`

* GitLab API:

  + https://docs.gitlab.com/ee/api/iterations.html
  + https://docs.gitlab.com/ee/api/group_iterations.html

Examples
--------

List the iterations for a project or a group::

    p_iterations = project.iterations.list()
    g_iterations = group.iterations.list()

You can filter the list using the following parameters:

* ``iids``: unique IDs of iterations for the project
* ``state``: either ``opened``, ``upcoming``, ``started``, ``closed``, or ``all`` iterations. Defaults to ``all``. 
* ``search``: search only iterations with a title matching the provided string.


::

    p_iterationss = project.iterations.list(state='closed')
    g_iterationss = group.iterations.list(state='opened')

Get a single iteration::

    p_iteration = project.iterations.get(interation_id)
    g_iteration = group.iterations.get(interation_id)

Create a iteration::

    iteration = project.iterations.create({'title': 'Week 22-23'})

Edit an interation::

    iteration.description = 'v 1.0 release'
    iterations.save()


List the issues related to a milestone::

    issues = iteration.issues()
