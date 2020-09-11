# bg-atom-utils package

# 2020-09 Status

As of 2020-09 this is a work in progress and is on its second version. The dependency between this and bg-redom-ui has flipped. That will evolve into an independent JS / DOM component library and this package will use that library to provide an Atom specific API.

A new feature in this release that I am excited about is the PolyfillObjectMixin pattern. I submitted several PR to Atom projects in the beginning of the year that have gotten no attention despite asking for advice in the atom slack group. This pattern allows me to publish Atom plugins that depend on those changes by including a dynamically applied patch which will automatically turn off if the PR is ever accepted.

I plan to organize the functions in this package with PolyfillObjectMixin so that they extend the Atom API object and therefore become easier to find and use.


# Summary

This is an NPM Package that provides utilities to for writing Atom plugins.

See the atom package bg-atom-packageDev (WIP) which (will) demonstrate how to use this package and provide some tools for development.

### Classes
  * class BGAtomPlugin :  base class for creating the main entrypoint for Atom packages.
  * class BGAtomView   :  base class for creating new Atom WorkspaceItems displayed in panes.
  * class PolyfillObjectMixin : base class for for managing dynamic extensions to Atom global object while waiting for PR to be accepted
  * class BGTimer       : class for simple timing of code
  * class BGFeedbackDialog :  class for displaying feedback for long tasks

### Functions
  * function WatchPackageStateChange(packageNames, callback)  : makes depending on other pkgs more convenient
  * function bgAsyncSleep(ms) : delay function to be used in sync functions
  * function FirstParamOf   : helper for overloaded function parameters
  * function ArrangeParamsByType   : helper for overloaded function parameters
  * function GetConfigKeys         : query for all matching atom config keys
  * function OnDidChangeAnyConfig  : watch for changes to multiple config keys at once
  * function DispatchCommand -- wrapper for atom.commands.dispatch on the active target
  * function BGRemoveKeybindings -- dynamically disable some keystroke from your package
  * function BGFindWorkspaceItemFromURI -- get an open URI if one exists
