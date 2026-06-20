# Pokopia Habitat Comfort Optimizer

A vanilla JavaScript optimization utility designed to calculate the best items for habitats based on pooled Pokémon favorite categories.

## Data Schema Requirements

The JavaScript functions expect two arrays of objects. If you are pulling this from a MySQL database via PHP, you can echo the data as JSON directly into `allPokemon` and `allItems` on page load.

### Pokémon Object Schema
```JSON
{
  "id": "bulbasaur",
  "name": "Bulbasaur",
  "spriteUrl": "path/to/sprite.png",
  "favoriteCategories": ["Cute", "Nature"]
}
```

### Item Object Schema
```JSON
{
  "id": "cushion_red",
  "name": "Red Cushion",
  "type": "Relaxation", // Must be exactly: "Toy", "Relaxation", or "Decoration"
  "imageUrl": "path/to/item.png",
  "categories": ["Cute", "Relaxing"]
}
```

### Notes
- HTML5/CSS3 and Vanilla ECMAScript 5/6.
- Calculation Logic functions handle the array intersections and sorting.
- Rendering Logic functions handle DOM insertion and can be easily stripped out if you intend to generate the markup server-side via PHP.

### Testing
Serve via a local server (e.g., python -m http.server 8000 from the /dist directory).

### Credits & Acknowledgements
- **Data Source:** Game data, category mapping, and imagery assets are sourced from [Serebii.net](https://www.serebii.net). All credit for the underlying database compilation goes to Joe Merrick and the Serebii team.
- **Habitat/Comfort Mechanics:** Idea for this adapted from community mechanics testing shared by [calmthesehands](https://www.reddit.com/user/calmthesehands) on the [r/Pokopia](https://www.reddit.com/r/Pokopia/comments/1ruvefs/did_some_testing_with_favorite_items_comfort/) subreddit.
