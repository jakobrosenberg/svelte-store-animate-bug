
<script>
    import {myStore} from '../myStores'
    myStore.update(store => store)
</script>

<div>
<h1>
This page updates the store. It also breaks navigation.
</h1>

<h3>Navigating here makes the previous page part of the layout</h3>
<br><br>
<div>
    Problem can be fixed by either of the following
    <ul>
        <li>not running <b>myStore.update(store => store)</b> outside of <b>setTimeout()</b> on the incoming page</li>
        <li>not having a visible <b>out:send={{ key: 'modal' }}</b> on the outgoing page</li>
        <li>having a small store</li>
    </ul>
    
</div>
</div>