   <template>
       <div class="col-sm-6 col-md-4 col-lg-3">
        <div class="panel panel-default">
            <div class="panel-body quote">
                <slot></slot>
            </div>
        </div>
    </div>
   </template>
<script>
export default {};
</script>
<style>
.panel-body {
  text-align: center;
  font-family: "Comic Sans Ms", cursive;
  font-size: 24px;
  color: #6e6e63;
}
.quote {
  cursor: pointer;
}
.quote:hover {
  background-color: #fefe34;
}
</style>
