<div class="card">
  <slot>Default Content</slot>
</div>

<!-- Props allow you to re-use compoenents by passing in different data 

Although props are greate for re-usability, we do have a strict parent-child relationship

The child will always be in control of the HTML content and the parent can only pass in different data values

Slots on the other hand are more powerful

They allow you to re-use a component 

They allow the parent component to control the content inside the child content

Slots allow a parent component to embed any content in a child component including HTML elements -->

<style>
  .card {
    box-shadow: 0 4px 8px 0 rgba(0, 0 , 0, 0.2);
    transition: 0.3s;
    padding: 16px;
    margin-bottom: 20px;
    width: 200px;

  }

  .card:hover {
    box-shadow: 0 8px 16px 0 rgba(0, 0 , 0, 0.2);
  }
</style>