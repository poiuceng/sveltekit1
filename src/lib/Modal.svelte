<script>
    import {onMount} from 'svelte';

    const close = () => {
        document.querySelector('.modal').style.opacity = 0;
        document.querySelector('.modal-backdrop').style.opacity = 0;
        setTimeout(() => {
            document.querySelector('.modal').style.display = 'none';
            document.querySelector('.modal-backdrop').style.display = 'none';
        }, 500);
    };



</script>
<div>
    <button class="btn btn-primary" on:click={() => {
        document.querySelector('.modal').style.display = 'block';
        document.querySelector('.modal-backdrop').style.display = 'block';
        setTimeout(() => {
            document.querySelector('.modal').style.opacity = 1;
            document.querySelector('.modal-backdrop').style.opacity = 1;
        }, 100);
    }}>Open Modal
    </button>
</div>

<div>
    <div class="modal">
        <div class="modal-content">
            <div class="modal-header">
                <h4 class="modal-title">Modal Header</h4>
            </div>
            <div class="modal-body">
                <p>Some text in the modal.</p>
                <p>Some other text...</p>
            </div>
            <div class="modal-footer">
                <button class="btn btn-default" on:click={close}>Close</button>
                <button class="btn btn-primary" on:click={close}>Save changes</button>
            </div>
        </div>
    </div>
    <div class="modal-backdrop"></div>
</div>

<style>
    .modal {
        display: none;
        position: fixed;
        z-index: 1;
        left: 0;
        top: 0;
        width: 100%;
        height: 100%;
        overflow: auto;
    }

    .modal-backdrop {
        display: none;
        position: fixed;
        z-index: 1;
        left: 0;
        top: 0;
        width: 100%;
        height: 100%;
        background-color: rgb(0, 0, 0);
        background-color: rgba(0, 0, 0, 0.4);
    }

    .modal-content {
        background-color: #fefefe;
        margin: 15% auto;
        padding: 20px;
        border: 1px solid #888;
        width: 80%;
    }

    .modal-header h4 {
        margin: 0;
    }

    .modal-footer {
        padding: 2px 16px;
        background-color: #5cb85c;
        color: white;
    }
</style>