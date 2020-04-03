<flexboxLayout class='flex-centered'>
    <label class='h1 text-center' text='page 1' />
</flexboxLayout>

<page>
    <actionBar title="Alcohol Money Calculator">
    </actionBar>
    <stackLayout class="p-20">
        <label text="What was the cost of the drink?" />
        <textField keyboardType="number" bind:text={cost}></textField>
        
        <label text="Amount" />
        <label bind:text={amount} />
        <button on:tap={handleAmount}>
            Amount?
         </button>}

        <label text="Percent Alc" />
        <label bind:text={percent} />
         <slider bind:value={percent}></slider>

        <label text="Cost per Drink" />         
        <label bind:text={costPerDrink} />
    </stackLayout>
</page>

<script>
    function handleAmount() {
        prompt('How many ounces?', '12')
        .then((res) => {
            amount = parseInt(res.text);
        })
    }
            
    let cost = 0; // use textField
    let amount = 1; // use Button to Prompt
    let percent = 5; // use slider
    $: costPerDrink = cost / (amount * (percent/100) / .6) || 0    
</script>