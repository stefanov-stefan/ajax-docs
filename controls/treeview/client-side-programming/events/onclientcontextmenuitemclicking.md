---
title: OnClientContextMenuItemClicking
page_title: OnClientContextMenuItemClicking | UI for ASP.NET AJAX Documentation
description: OnClientContextMenuItemClicking
slug: treeview/client-side-programming/events/onclientcontextmenuitemclicking
tags: onclientcontextmenuitemclicking
published: True
position: 27
---

# OnClientContextMenuItemClicking



## 

The __OnClientContextMenuItemClicking__ client-side event occurs when the user clicks a menu item, but before the __OnClientContextMenuItemClicked__event fires. The event is called just prior to postback or url redirection and can be canceled.

The event handler receives parameters:

1. The treeview instance that fired the event.

1. Event arguments with functions:

* __get_menuItem()__ retrieves a reference to the selected context menu item.

* __get_node()__ retrieves a reference to the clicked on node.

* __set_cancel()__ call this function to specify wether the event should be canceled (true) or not (false).

* __get_domEvent()__ retrieves the DOM event object of the item click.

The example below shows how to cancel the event if the text of the menu item is "Search"

````ASPNET
	
	    <script type="text/javascript" language="javascript">
	        function ClientContextMenuItemClicking(sender, eventArgs) {
	            var node = eventArgs.get_node();
	            var item = eventArgs.get_menuItem();
	
	            if ((item.get_text() == "Network Search") && (node.get_text() == "Printers")) {
	                eventArgs.set_cancel(true);
	            }
	        }
	    </script>
	
	    <telerik:RadTreeView ID="RadTreeView1" runat="server" OnClientContextMenuItemClicking="ClientContextMenuItemClicking">
	    </telerik:RadTreeView>
````



# See Also

 * [RadTreeNode]({%slug treeview/client-side-programming/objects/radtreenode%})

 * [OnClientContextMenuItemClicked]({%slug treeview/client-side-programming/events/onclientcontextmenuitemclicked%})

 * [OnClientContextMenuShowing]({%slug treeview/client-side-programming/events/onclientcontextmenushowing%})

 * [OnClientContextMenuShown]({%slug treeview/client-side-programming/events/onclientcontextmenushown%})