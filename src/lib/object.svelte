<script>
    export let text;
    import qrcode from 'qrcode'
    import { beforeUpdate } from 'svelte';
    let canvasElement;
    const render = () => {
        qrcode.toCanvas(canvasElement, `https://downpng.roto.win/download#${text}`, function (error) {
            if (error) console.error(error)
            console.log(`Rendered ${text}`);
        })
    };
    beforeUpdate(() => {
        if (text == null) return;
        if (canvasElement == null) return;
		render();
	});
</script>

<obj>
    
    <main>
        <badge>
            H-World Event
        </badge>
        <txt>
            다운로드 코드는
            <code>
                {text}
            </code>
            입니다.
        </txt>
        <p>오른쪽 QR코드를 스캔하거나 https://downpng.roto.win/ 에서 사진을 다운로드해주시길 바랍니다.</p>
        <p>사진 다운로드는 2021-12-25 오후 4시 이전에 열릴 예정입니다.</p>
    </main>
    <sub>
        
        <canvas bind:this={canvasElement} width="40px" height="40px"></canvas>
    </sub>
    
</obj>

<style>
    obj {
        display: flex;
        align-items: center;
        justify-content: space-around;
        border: 1px solid black;
        padding: 10px;
        width: 800px;
        break-inside: avoid;
    }
    main {
        display: flex;
        flex-direction: column;
        align-items: center;
        font-weight: 300;
    }
    main badge {
        padding: 10px;
        font-weight: 100;
        font-size: 25px;
        margin-bottom: 10px;
    }
    main txt code {
        font-size: 20px;
        font-weight: 800;
    }
    sub {
        display: flex;
        flex-direction: column;
    }
    p {
        margin: 0;
    }
</style>