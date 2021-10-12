# git-diff-demo

Demonstrates git diff commands between branches

This repository's git tree looks like this (excluding the commit that adds this README file):

```
  B---E
 /
A---D
 \ /
  C
```


## Two-dot Diff Command

A two-dot diff command shows ALL changes between the two branches, including changes made to the base branch after the featre branch was forked.

```bash
$ git diff master..branch-a

diff --git a/file-a.txt b/file-a.txt
new file mode 100644
index 0000000..0f1090f
--- /dev/null
+++ b/file-a.txt
@@ -0,0 +1 @@
+from branch a
diff --git a/file.txt b/file.txt
index 22b7b22..e69de29 100644
--- a/file.txt
+++ b/file.txt
@@ -1 +0,0 @@
-from branch b
diff --git a/file2.txt b/file2.txt
new file mode 100644
index 0000000..9de77c1
--- /dev/null
+++ b/file2.txt
@@ -0,0 +1 @@
+f2
```

## Three-dot Diff Command

A three-dot diff command only shows the diff between the feature branch and the most recent common ancestor commit on the base branch (i.e. the commit that the feature branch was forked from)

```bash
$ git diff master...branch-a

diff --git a/file-a.txt b/file-a.txt
new file mode 100644
index 0000000..0f1090f
--- /dev/null
+++ b/file-a.txt
@@ -0,0 +1 @@
+from branch a
diff --git a/file2.txt b/file2.txt
new file mode 100644
index 0000000..9de77c1
--- /dev/null
+++ b/file2.txt
@@ -0,0 +1 @@
+f2
```

Note how file.txt does not appear in the three-dot diff commmand while it *does* appear in the two-dot version.
