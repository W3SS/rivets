Use the `data-each-[item]` binding to have Rivets.js automatically loop over items in an array and append bound instances of that element. Within that element you can bind to the iterated item as well as any contexts that are available in the parent view.

    <ul>
      <li data-each-todo="list.todos">
        <input type="checkbox" data-checked="todo.done">
        <span data-text="todo.summary"></span>
      </li>
    <ul>

If the array you're binding to contains non-model objects (they don't conform to your adapter), you can still iterate over them, just make sure to use the adapter bypass syntax --- in doing so, the iteration binding will still update when the array changes, however the individual items will not since they'd be bypassing the `adapter.subscribe`.

    <ul>
      <li data-each-link="item.links">
        <a data-href="link:url" data-text="link:title"></a>
      </li>
    </ul>

Also note that you may bind to the iterated item directly on the parent element.

    <ul>
      <li data-each-tag="item.tags" data-text="tag:name"></li>
    </ul>