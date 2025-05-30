<template>
    <div class="container row">
        <div class="card col-5" style="width: 800px;">
            <h1>TEST Youtube</h1>
            <vue-plyr>
                <div data-plyr-provider="youtube" data-plyr-embed-id="bTqVqk7FSmY"></div>
            </vue-plyr>
            <vue-plyr>
                <div class="plyr__video-embed">
                    <iframe
                        src="https://www.youtube.com/watch?v=wAJU1wbeRgc"
                        allowfullscreen allowtransparency allow="autoplay"></iframe>
                </div>
            </vue-plyr>
        </div>
    </div>
    <!-- youtube div element -->

</template>