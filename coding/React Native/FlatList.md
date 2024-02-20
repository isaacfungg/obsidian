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

```js

import { createNativeStackNavigator } from '@react-navigation/native-stack';
const Stack = createNativeStackNavigator();

function App() {
  return (
    <NavigationContainer>
      <Stack.Navigator initialRouteName="ProductList">
        <Stack.Screen name="ProductList" component={ProductListScreen} />
        <Stack.Screen name="ProductDetails" component={ProductScreen} />
      </Stack.Navigator>
    </NavigationContainer>
  );
}

```



```js

const ProductListScreen = ({ navigation }) => {
  const renderItem = ({ item }) => (
    <TouchableOpacity onPress={() => navigation.navigate('ProductDetails', { product: item })}>
      <Image source={{ uri: item.iconUri }} style={{ width: 50, height: 50 }} />
      {/* Render other product info if needed */}
    </TouchableOpacity>
  );

  return (
    <FlatList
      data={yourProductData} // Your product data here
      renderItem={renderItem}
      keyExtractor={item => item.id.toString()}
      horizontal={true}
    />
  );
};


const ProductScreen = ({ route, navigation }) => {
  // Extracting the passed product details
  const { product } = route.params;

  // Directly use product details for rendering
  return (
    <ScrollView>
      <Image source={{ uri: product.mainImageUri }} style={{ width: '100%', height: 200 }} />
      <Text>{product.price}</Text>
      <Text>{product.description}</Text>
      {/* Render additional product details as needed */}
    </ScrollView>
  );
};


```