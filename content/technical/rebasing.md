Title: 
Date: 2014-05-01 11:41
Category: 
Tags: 
Slug: 
Lang: en
Author: ihommmani
Status: draft
Summary: How to render git branching alive

# Rebasing onto

I used git for the first time two years ago. 
At that time I only knew some of the basic commands such as status, add, commit and push/pull.
For a time it was good. But since I have read pro git I realize that I greatly underused this powerfull tool. 
In this small article, I want to share my vision of a simple option of the rebase command, the onto option.

## Git and branching
From my point of view, git branching system is really THE killer feature of git. 
To make things simple, we can consider a branch as pointer to a git commit. It's nothing more. 
Simple insn't it ?
Branches are hence lightweight objects we can create, merge and rebase at will. 
It's the action of rebasing which interest me, and in particular in association with the onto option.

With git when you create branch you can precise a base to that branch. By default it's the current branch but it can be whatever branch. 
Just type the following command:

```
git branch [foo_branch] [base_branch]
```
or more pragmatically, 

```
git checkout -b [foo_branch] [base_branch]
```

If you do not precise the base branch, git considers the current branch as the default base branch.

I wasn't aware of the fact that the original base branch can be changed at will. 
It's here where the onto option appears. 

Like a gardener you can decide to cut your branch and graft it onto another branch, ie give it a new base.

Now why would I do that ?

## How it works
Simply put: 
'''
git rebase --onto [new_base] [former_branch_base] [branch_head]
'''
Now former_branch_base will now point to the new_base, and we will have the following scheme:


Remember we said branches are nothing more than pointers to commits ?
Knowing that, you can also replace branch name by commit which comes handy when we use the following trick to erase some commits.
Indeed nothing prevent us from considering new_base, former_branch_base and branch_name as parts of the same branch.
That way we can shorten it, ie erase commits.
Consider the following branch:


If we run the following command:
```
```

We'll now have:


Notice that the commits disapeared. 
Also this is fine, interactive rebase is a better option to erase commits. 

# Conclusion
We have seen that git branches are all but motion less. You can define bases very easily.
