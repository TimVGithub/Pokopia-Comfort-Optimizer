# Pokopia Habitat Comfort Optimizer

A vanilla JavaScript optimization utility designed to calculate the best items for habitats based on pooled Pokémon favorite categories[cite: 7].

## Data Schema Requirements

The JavaScript functions expect two arrays of objects[cite: 7]. If you are pulling this from a MySQL database via PHP, you can echo the data as JSON directly into `allPokemon` and `allItems` on page load[cite: 7].

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
  "type": "Relaxation", // Must be exactly: "Toy", "Relaxation", "Decoration", or "None"
  "imageUrl": "path/to/item.png",
  "categories": ["Cute", "Relaxing"]
}
```

## Notes
* HTML5/CSS3 and Modern Vanilla ECMAScript (ES6+).
* Calculation Logic functions handle the array intersections, duplicate entry tracking, and ranking sorts.
* Rendering Logic functions manage zero-dependency DOM injections using performance-focused `DocumentFragment` buffering. These can be cleanly stripped out if you intend to handle layout generation server-side via PHP.

## Testing
* Try here: https://timvgithub.github.io/Pokopia-Comfort-Optimizer/
* Serve via a local server (e.g., `python -m http.server 8000` from the workspace directory).

## Credits & Acknowledgements
* **Data Source**: Game data, category mapping, and imagery assets are sourced from [Serebii.net](https://www.serebii.net). All credit for the underlying database compilation goes to Joe Merrick and the Serebii team.
* **Habitat/Comfort Mechanics**: Idea for this adapted from community mechanics testing shared by [calmthesehands](https://www.reddit.com/user/calmthesehands) on the [r/Pokopia](https://www.reddit.com/r/Pokopia/comments/1ruvefs/did_some_testing_with_favorite_items_comfort/) subreddit.