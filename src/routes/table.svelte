<script>
    const print = () => window.print();
    let list = "aaaaaa\naaaaaa\naaaaaa\naaaaaa\naaaaaa\naaaaaa\naaaaaa\naaaaaa\naaaaaa\naaaaaa\naaaaaa";
</script>
<noprint>
아래에 필요한 문자열을 \n (line break) 별로 배치해주세요.
<textarea name="Text1" cols="40" rows="5" bind:value={list}></textarea>
<button on:click={print}>인쇄</button>
</noprint>

<div class="list">
    <table>
        <tr>
            <th colspan="1">순서</th>
            <th colspan="1">코드</th>
            <th colspan="30">시간</th>
            <th colspan="30">비고</th>
        </tr>
        <tr>
            <td colspan="1">#0</td>
            <td colspan="1">TESTCODE</td>
            <td colspan="30">1 21</td>
            <td colspan="30">기각처리됨</td>
        </tr>
        {#each list.split("\n") as item, idx}
        <tr>
            <td colspan="1">#{idx+1}</td>
            <td colspan="1">{item}</td>
            <td colspan="30"></td>
            <td colspan="30"></td>
        </tr>
        {/each}
    </table>
</div>
<style>
table {
    width: 100%;
}
tr {
    break-inside: avoid;
}
th, td {
    border: 1px solid #444444;
    padding: 10px;
}
noprint {
    display: flex;
    flex-direction: column;
}
@media print {
    noprint {
        display: none;
    }
}
</style>