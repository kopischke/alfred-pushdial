[![Stories in Ready](http://badge.waffle.io/kopischke/alfred-pushdial.png)](http://waffle.io/kopischke/alfred-pushdial)  
# Dial with PushDialer workflow for Alfred 2

An [Alfred 2 workflow][alfred] making it easy to dial phone numbers from OS X contacts, text selected in any OS X application, or the Alfred prompt with [PushDialer][pushdialer]. Note you need the [Alfred Powerpack][alfred-powerpack] to enable workflows.

![Dial with PushDialer workflow overview](doc/pushdialer-workflow.png)

## Usage

### Using it with OS X contacts

The workflow offers two different ways to dial addresses retrieved from OS Xb  contacts store with Alfred:

1. it defines a custom contacts action which will dial a number when actioned from Alfredb s contacts viewer. For this to work, assign the b Dialb  action to phone numbers in Alfredb s Contacts settings (found in *Preferences B; Features B; Contacts B; Contacts*):

    ![Alfred Contacts custom action settings](doc/pushdialer-contacts-settings.png)
    
2. it offers a `call` keyword that will return phone numbers for contacts matching the query, right in the Alfred result window:

    ![Alfred call keyword usage example](doc/pushdialer-call.png)

    `call` returns the first found of the mobile, home, work or main phone numbers, or pager number, for contacts whose name, nickname or company name matches the query. If you want to specifically target home, work or mobile numbers, `call`b s brethren `callh`, `callw` and `callm` will do your bidding.
    
    Note the search is incremental: every query word is matched to the result set individually, which allows you to refine the results using only partial queries:
    
    ![Alfred call keyword usage example](doc/pushdialer-call-incremental.png)
    
    Query word matching is case agnostic for words in all lower case, case sensitive otherwise (i.e. b Coolb  finds b Liquid Coolants Ltd.b , but not b Mancoolieb , while b coolb  finds both).

### Using it with text selected in OS X applications

There are two hotkeys defined to get selected text into the workflow: the first will run the selected text straight through the dial routine, the other will put it into the Alfred prompt, ready to execute. Note Alfred strips the keyboard shortcuts on workflow installation, so you will have to set your own *Preferences B; Workflows B; Dial with PushDialer*.

### Using it from the Alfred prompt

The workflow defines a `dial` keyword: any query that follows it is passed to the dial routine.

![Alfred dial keyword usage example](doc/pushdialer-dial.png)

## Updating

Dial with PushDialer supports [Alleyoop][alleyoop] for automated updates. [Install Alleyoop][alleyoop-download] and do `oop`.

## Known bugs

1. If you miss mobile numbers in feedback, make sure the phone label in the Contacts application is not set to b iPhoneb  b  that label is not recognized by the utility used to query the contacts store \[[Issue #1](../../issues/1)\].
2. Others maybe, probably. Check the [Issues](../../issues) section. Create a new issue if you think you have found one that is not reported there.

## Credits and License

Inspired by the PushDialer workflow by [Florian Pellet][pellet-workflows].

The `call` keyword family relies on the [*contacts* utility by Shane Celis][contacts-util] to provide its results. Contacts is licensed under the GPL version 2. As it is distributed with the workflow, this means the Dial with PushDialer workflow is also distributed under the terms of the [General Public License version 2][gpl2].

## Contributing

1. fork the repo (bonus points for creating a feature branch)
2. commit you changes
3. make sure you havenb t broken anything (even better: write some tests!)
4. submit a pull request

[alfred]:           http://www.alfredapp.com
[alfred-powerpack]: http://www.alfredapp.com/powerpack/
[alleyoop]:         http://alfred.daniel.sh
[alleyoop-download]:http://alfred.daniel.sh/Workflows/Alleyoop.alfredworkflow
[contacts-util]:    http://www.gnufoo.org/contacts/contacts.html
[gpl2]:             http://www.gnu.org/licenses/gpl-2.0.html
[pellet-workflows]: http://florianpellet.com/alfred/
[pushdialer]:       http://pushdialer.com
