***
```js
<Flatlist
	data={list}
	renderItem{({item}) => {
		return (
			<View>
				<Text>{$item}</Text>
			</View>
		);
	}}
	horizontal
/>
```