# Easily Run Drafts Actions Via Editorial Workflows

_Captured: 2015-06-09 at 20:58 from [unapologetic.io](http://unapologetic.io/posts/2014/01/25/easily-run-drafts-actions-via-editorial-workflows/)_

(▼)

While building Editorial workflows, I've often run into times in which I wanted to launch Drafts and run an action that I've previously built and have in my URL action library. I've grown tired of having to remember and put together the necessary blocks in Editorial, so I created a couple generic groups of actions to save as presets so that I can easily add Drafts actions into my Editorial workflows.

The groups of actions are bundled as their own workflow. Import the workflow into Editorial, then choose edit. There are two options for the presets, one for a simple Drafts action which creates a new Draft from your input text and runs a single action on it, and one for a chained Drafts action which creates a Draft from your input and runs an action on it, then chains back and creates another draft from the input and runs another action on it. Since I'm not aware of any standard way to bundle groups of actions, I placed each set within an "if.. end if" block. Save the block as the preset, then each time you want to use it just drag the if.. part down to the bottom so that the actions pop out and then delete it. There's a brief video below showing how easy it is to use this to add a Drafts action into your Editorial workflows.

One last note: remember that the action title in the first action needs to be manually URL encoded, and the action in the chained URL needs to manually _double_ URL encoded. Same with the input, but the action groups do that for you.

[Direct Import Link for the "Drafts Actions" workflow.](editorial://add-workflow?workflow-data=%7B%22name%22%3A%20%22Drafts%20Actions%22%2C%20%22actions%22%3A%20%5B%7B%22pauseWithoutShowingParameters%22%3A%20false%2C%20%22pauseBeforeRunning%22%3A%20false%2C%20%22customTitle%22%3A%20%22Single%20Drafts%20Action%22%2C%20%22parameters%22%3A%20%7B%22expression1%22%3A%20%7B%22text%22%3A%20%22%3F%22%2C%20%22tokenRanges%22%3A%20%7B%22%7B0%2C%201%7D%22%3A%20%22Input%22%7D%2C%20%22type%22%3A%20%22advancedText%22%7D%2C%20%22expression2%22%3A%20%7B%22text%22%3A%20%22%22%2C%20%22tokenRanges%22%3A%20%7B%7D%2C%20%22type%22%3A%20%22advancedText%22%7D%2C%20%22comparisonType%22%3A%200%7D%2C%20%22class%22%3A%20%22WorkflowActionCondition%22%7D%2C%20%7B%22pauseWithoutShowingParameters%22%3A%20false%2C%20%22pauseBeforeRunning%22%3A%20false%2C%20%22customTitle%22%3A%20%22%22%2C%20%22parameters%22%3A%20%7B%7D%2C%20%22class%22%3A%20%22WorkflowActionURLEscape%22%7D%2C%20%7B%22pauseWithoutShowingParameters%22%3A%20false%2C%20%22pauseBeforeRunning%22%3A%20false%2C%20%22customTitle%22%3A%20%22Run%20Drafts%20Action%22%2C%20%22parameters%22%3A%20%7B%22URL%22%3A%20%7B%22text%22%3A%20%22drafts%3A%2F%2Fx-callback-url%2Fcreate%3Ftext%3D%3F%26action%3D%5BENCODED%20ACTION%5D%22%2C%20%22tokenRanges%22%3A%20%7B%22%7B36%2C%201%7D%22%3A%20%22Input%22%7D%2C%20%22type%22%3A%20%22advancedText%22%7D%2C%20%22waitUntilLoaded%22%3A%20false%2C%20%22revealBrowserAutomatically%22%3A%20true%2C%20%22openIn%22%3A%201%7D%2C%20%22class%22%3A%20%22WorkflowActionOpenURL%22%7D%2C%20%7B%22pauseWithoutShowingParameters%22%3A%20false%2C%20%22pauseBeforeRunning%22%3A%20false%2C%20%22customTitle%22%3A%20%22%22%2C%20%22parameters%22%3A%20%7B%7D%2C%20%22class%22%3A%20%22WorkflowActionConditionEnd%22%7D%2C%20%7B%22pauseWithoutShowingParameters%22%3A%20false%2C%20%22pauseBeforeRunning%22%3A%20false%2C%20%22customTitle%22%3A%20%22x-callback%20Drafts%20Action%22%2C%20%22parameters%22%3A%20%7B%22expression1%22%3A%20%7B%22text%22%3A%20%22%3F%22%2C%20%22tokenRanges%22%3A%20%7B%22%7B0%2C%201%7D%22%3A%20%22Input%22%7D%2C%20%22type%22%3A%20%22advancedText%22%7D%2C%20%22expression2%22%3A%20%7B%22text%22%3A%20%22%22%2C%20%22tokenRanges%22%3A%20%7B%7D%2C%20%22type%22%3A%20%22advancedText%22%7D%2C%20%22comparisonType%22%3A%200%7D%2C%20%22class%22%3A%20%22WorkflowActionCondition%22%7D%2C%20%7B%22pauseWithoutShowingParameters%22%3A%20false%2C%20%22pauseBeforeRunning%22%3A%20false%2C%20%22customTitle%22%3A%20%22%22%2C%20%22parameters%22%3A%20%7B%7D%2C%20%22class%22%3A%20%22WorkflowActionURLEscape%22%7D%2C%20%7B%22pauseWithoutShowingParameters%22%3A%20false%2C%20%22pauseBeforeRunning%22%3A%20false%2C%20%22customTitle%22%3A%20%22%22%2C%20%22parameters%22%3A%20%7B%22name%22%3A%20%22Single%20Encoded%20Input%22%2C%20%22value%22%3A%20%7B%22text%22%3A%20%22%3F%22%2C%20%22tokenRanges%22%3A%20%7B%22%7B0%2C%201%7D%22%3A%20%22Input%22%7D%2C%20%22type%22%3A%20%22advancedText%22%7D%7D%2C%20%22class%22%3A%20%22WorkflowActionStoreVariable%22%7D%2C%20%7B%22pauseWithoutShowingParameters%22%3A%20false%2C%20%22pauseBeforeRunning%22%3A%20false%2C%20%22customTitle%22%3A%20%22%22%2C%20%22parameters%22%3A%20%7B%7D%2C%20%22class%22%3A%20%22WorkflowActionURLEscape%22%7D%2C%20%7B%22pauseWithoutShowingParameters%22%3A%20false%2C%20%22pauseBeforeRunning%22%3A%20false%2C%20%22customTitle%22%3A%20%22Run%20Drafts%20Action%22%2C%20%22parameters%22%3A%20%7B%22URL%22%3A%20%7B%22text%22%3A%20%22drafts%3A%2F%2Fx-callback-url%2Fcreate%3Ftext%3D%3F%26action%3D%5BENCODED%20ACTION%5D%26x-success%3Ddrafts%253A%252F%252Fx-callback-url%252Fcreate%253Ftext%253D%3F%2526action%253D%5BDOUBLE%20ENCODED%20ACTION%202%5D%22%2C%20%22tokenRanges%22%3A%20%7B%22%7B120%2C%201%7D%22%3A%20%22Input%22%2C%20%22%7B36%2C%201%7D%22%3A%20%22Single%20Encoded%20Input%22%7D%2C%20%22type%22%3A%20%22advancedText%22%7D%2C%20%22waitUntilLoaded%22%3A%20false%2C%20%22revealBrowserAutomatically%22%3A%20true%2C%20%22openIn%22%3A%201%7D%2C%20%22class%22%3A%20%22WorkflowActionOpenURL%22%7D%2C%20%7B%22pauseWithoutShowingParameters%22%3A%20false%2C%20%22pauseBeforeRunning%22%3A%20false%2C%20%22customTitle%22%3A%20%22%22%2C%20%22parameters%22%3A%20%7B%7D%2C%20%22class%22%3A%20%22WorkflowActionConditionEnd%22%7D%5D%2C%20%22description%22%3A%20%22%22%7D)