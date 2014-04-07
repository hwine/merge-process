===========================
Merge Day team interactions
===========================

The below diagram is constructed from the existing wiki page headers,
and the email we set up. In setting this up, a few interactions were
missed. Those all have "(new)" in the description below. During run, we
found some key events buried down a link path, those are marked "(pulled
forward)".

The wiki page used for each column is:

    - RelMan Gecko - https://wiki.mozilla.org/Release_Management/Merge_Documentation
    - RelMan Gecko (now releng) - https://wiki.mozilla.org/Release_Management/Merge_Documentation
    - RelEng Gaia - https://wiki.mozilla.org/ReleaseEngineering/Merge_Duty/Central_will_become_an_odd_numbered_Gecko_version

.. actdiag::
    :desctable:

    actdiag {

        a ->
        a1 ->
        n11 ->
        n12 ->
        n16 ->
        a2 ->
        a3 ->
        a4 ->
        a5 ->
        a6 ->
        b2g_d_6 ->
        a7 ->
        a71 ->
        n17 ->
        a711 ->
        a712 ->
        a72 ->
        a721 ->
        a722 ->
        a723 ->
        a724 ->
        a725 ->
        a73 ->
        a731 ->
        a732 ->
        a733 ->
        a734 ->
        a735 ->
        a736 ->
        a737 ->
        a738 ->
        a739 ->
        b ->
        c ->
        c1 
        # clear to restart vcs-sync
        b -> n21 -> n15

        b2g_d  ->
        b2g_d_1  ->
        b2g_d_2  ->
        b2g_d_3  ->
        b2g_d_3_1  ->
        b2g_d_4  ->
        b2g_d_5  ->
        b2g_d_6  ->
        b2g_d_7  ->
        n23 ->
        n24 ->
        b2g_d_8  ->
        b2g_d_9  ->
        b2g_d_10  ->
        b2g_d_11  ->
        b2g_d_12  ->
        b2g_d_13  ->
        n15 ->
        b2g_e ->
        b2g_e_1  ->
        b2g_e_2 
        # link preconditions for Beta 1 GTB
        b2g_d_10  -> n14 -> n13
        a725 -> n13
        # join readiness for vcs-sync to be re-enabled
        b2g_d_13  -> n15

        # all done
        c1 -> n22 -> n18


        lane {
            label = "RelMan Gecko"
            a  [color = "lightgreen", label = "Start Merge!", description = "Merge Day (Central, Aurora, Beta)"]
            n16 [color = "lightgreen", shape = "diamond", color = "lightblue", label = "notify start",
            description = "email to dev-planning, irc #developers that
            merge started (new)"]
            a1  [color = "lightgreen", label = "IID check", description = "Check IIDs that need to be bumped"]
            n11 [color = "lightgreen", label = "Locale check", description = "Confirm Locales for merged branches (new)"]
            n12 [color = "lightgreen", label = "Go for RelEng", description = "Give go to RelEng with above information (new)"]
            n13 [label = "ready to give\nGTB for b1", description = "Build the Beta can happen at any time (new)."]
            n18 [shape = "diamond", color = "lightblue", label =
                "Notify DONE", description = "email dev-planning, irc
                #developers, that merge is complete (new)"]
            }
        lane {
            label = "RelMan Gecko\n(now releng)"
            a2  [color = "lightgreen", label = "pull repos", description = "Get all of the Repos"]
            a3  [color = "lightgreen", label = "config to push", description = "Set each Repo up for Pushing"]
            a4  [color = "lightgreen", label = "hg extension", description = "Set up HG Extensions"]
            a5  [color = "lightgreen", label = "Close Trees!!!!", description = "Close the Trees"]
            a6  [color = "lightgreen", label = "stop vcs sync\n(both)", description = "Ping Release Engineering"]
            a7  [color = "lightgreen", label = "get script", description = "Get Helper Script (do this every merge day)"]
            a71  [color = "lightgreen", label = "bump m-c", description = "mozilla-central tag/bump from 30 to 31"]
            n17 [shape = "diamond", color = "lightgreen", label = "notify\nbump mp",
                description = "email dev-planning; irc #developers (new)"]
            a711  [color = "lightgreen", label = "prep & tag", description = "Preparation and Tagging"]
            a712  [color = "lightgreen", label = "push m-c changes", description = "Verify & Push Your Changes"]
            a72  [color = "lightgreen", label = "m-a => m-b", description = "mozilla-aurora 29 to mozilla-beta uplift"]
            a721  [color = "lightgreen", label = "push m-a", description = "Review tagging of mozilla-aurora and push"]
            a722  [color = "lightgreen", label = "tag & push m-b", description = "Review tagging of mozilla-beta and continue to push"]
            a723  [color = "lightgreen", label = "uplift", description = "Verify the script Pulled from Aurora into Beta"]
            a724  [color = "lightgreen", label = "check branding", description = "Verify the Commits related to version bumps and branding changes"]
            a725  [color = "lightgreen", label = "push & clobber\n(m-b)", description = "Clobber & push"]
            a73  [color = "lightgreen", label = "m-c => m-a", description = "mozilla-central 30 to mozilla-aurora uplift"]
            a731  [color = "lightgreen", label = "verify\nAurora Throttle", description = "Don't forget to throttle the Aurora channel"]
            a732  [color = "lightgreen", label = "push m-c", description = "Script will Tag and commit, continue to push"]
            a733  [color = "lightgreen", label = "uplift", description = "Verify that script Pulled from m-c into Aurora"]
            a734  [color = "lightgreen", label = "check branding", description = "Verify the Diff/Commit of Version Bumps/Branding changes"]
            a735  [color = "lightgreen", label = "check profiling", description = "Verify the Diff/Commit of profiling changes"]
            a736  [color = "lightgreen", label = "check dtrace", description = "Verify the Diff/Commit of mozconfig dtrace & instruments changes (had trouble last time the change manually if needed)"]
            a737  [color = "lightgreen", label = "l10n changes", description = "L10n data changes"]
            a738  [color = "lightgreen", label = "commit l10n", description = "Verify & Commit l10n changes"]
            a739  [color = "lightgreen", label = "push m-a & clobber", description = "Clobber & push"]
            b  [color = "lightgreen", label = "complete merge", description = "Completing the Merge"]
            n21  [color = "lightgreen", label = "clear to\nrestart vcs-sync", description = "Ask for vcs-sync to be restarted (new)"]
            c  [color = "lightgreen", label = "update wiki", description = "Change Template Version Numbers"]
            c1  [color = "lightgreen", label = "update templates", description = "Calculating the current Firefox release # and next release date"]
            n22 [ label = "Report DONE", description = "Inform RelMan merges are done (new)"]
            }
        lane {
            label = "RelEng Gaia"
            b2g_d [color = "lightgreen", label = "Merge Day!"]
            b2g_d_1 [color = "lightgreen", label = "branch b2g", description = "Create new b2g git branches"]
            b2g_d_2 [color = "lightgreen", label = "vcs_sync prep", description = "Bump gecko_git vcs-sync"]
            b2g_d_3 [color = "lightgreen", label = "bump bb-c gecko", description = "bump the other buildbot-config gecko versions"]
            b2g_d_3_1 [color = "lightgreen", label = "land patches", description = "And any other patches that needed to land before the migration"]
            b2g_d_4 [color = "lightgreen", label = "Aurora throttle", description = "throttle Aurora updates"]
            b2g_d_5 [color = "lightgreen", label = "Gecko version bump", description = "ReleaseEngineering/Merge_Duty/Steps#Bump_gecko_git_vcs-sync__28odd_numbered_central_gecko_version_29"]
            b2g_d_6 [color = "lightgreen", label = "pause both vcs-sync", description = "Pause Gecko l10n vcs-sync"]
            b2g_d_7 [color = "lightgreen", label = "wait for\ngecko merge", description = "perform the mozilla-aurora -> mozilla-beta & mozilla-central -> mozilla-aurora migrations"]
            n23 [color = "lightgreen", label = "start nightly", description = "Start nightly
            on m-c as soon as possible (pulled forward)"]
            n24 [color = "pink", label = "update bouncer", description = "Update bouncer
            for new location (pulled forward)"]
            b2g_d_8 [color = "lightgreen", label = "Gecko on m-a bump", description = "Merge the b2g version from central to aurora"]
            b2g_d_9 [color = "lightgreen", label = "EOL b2g Branch", description = "EOL a B2G branch, if appropriate"]
            b2g_d_10 [color = "lightgreen", label = "restart vcssync\n(for l10n)", description = "Restart Gecko l10n"]
            n14 [color = "lightgreen", label = "tell RelMan" description = "Let RelMan know b2g is ready (new)"]
            b2g_d_11 [color = "lightgreen", label = "tag MERGEDAY", description = "Tag B2G Gecko+Gaia for MERGEDAY"]
            b2g_d_12 [color = "lightgreen", label = "hg bundle creation", description = "Create new hg bundles"]
            b2g_d_13 [label = "notify dev-b2g", description = "dev_b2g newsgroup post"]
            n15 [color = "lightgreen", label = "restart vcs-sync", description = "vcs sync is ready to be re-enabled (new)"]
            b2g_e [label = "Much Later...", description = "Post merge day"]
            b2g_e_1 [label = "unthrottle Aurora", description = "Around the Friday of merge week, RelMan will be ask to Unthrottle Aurora nightly updates"]
            b2g_e_2 [label = "doc update", description = "Update this documentation"]
        }
    }

Doc notes
=========

- on odd number, no need to pause new gecko-git.py vcs sync -- follow
  the diagram and you don't get there too early.

- one (first?) tag command is missing a space before the '-m', so commit
  message becomes part of the tag name. RyanVM to correct for 29.

- template to create bug doesn't properly escape the '@' in email
  addresses.

- order of operations not correct for Gaia. Restarting vcs-sync is
  needed prior to deploy Gecko on m-a bump

- make more visible the `nightly kickoff`_ required

- note MERGEDAY tag on b2g is for security team

- not entirely clear how soon we can give okay for beta 1 to relman.
  Some of those steps may need re-ordering.


.. _`nightly kickoff`: https://wiki.mozilla.org/ReleaseEngineering/Merge_Duty/Steps#Perform_mozilla-aurora_-.3E_mozilla-beta_and_mozilla-central_-.3E_mozilla-aurora_migrations
