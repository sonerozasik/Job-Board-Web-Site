<template>
    <transition name="modal">
      <div class="modal-mask">
        <div class="modal-wrapper">
          <div class="modal-container">
            <div class="modal-header">
              <slot name="header">
                Default header
              </slot>
            </div>
            <div class="modal-body">
              <slot name="body">
                Default body
              </slot>
            </div>
            <div class="modal-footer">
              <slot name="footer">
                <button class="btn btn-primary" @click="$emit('close')">Close</button>
              </slot>
            </div>
          </div>
        </div>
      </div>
    </transition>
  </template>
  
  <style>
  .modal-mask {
    position: fixed;
    z-index: 9998;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, .5);
    display: table;
    transition: opacity .3s ease;
  }
  
  .modal-wrapper {
    display: table-cell;
    vertical-align: middle;
  }
  
  .modal-container {
    width: 500px;
    margin: 0px auto;
    padding: 20px 30px;
    background-color: #fff;
    border-radius: 2px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, .33);
    transition: all .3s ease;
    font-family: Helvetica,
  }