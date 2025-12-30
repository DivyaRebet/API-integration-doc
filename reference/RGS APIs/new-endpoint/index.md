---
title: Games Information and Configuration
excerpt: >-
  Explore detailed endpoints for game configurations, including titles,
  providers, categories, and bet options.
hidden: false
link:
  new_tab: false
---
## Games Information

This section provides detailed endpoints that return game configurations available to the client. The data includes only the games and configurations currently available to the client. Each game includes key attributes such as:

- **Title**: The name of the game.
- **Provider**: The company or entity that provides the game.
- **Category**: The genre or type of the game.
- **Available Bet Options**: The different betting options available for the game.

Additional related data may also be included, providing a comprehensive overview of each game's configuration.

### How to Use

To access the game configurations, use the provided endpoints. These endpoints will return the necessary data in a structured format, allowing for easy integration and use within your applications.

### Example

Here's an example of how the data might be structured:

```json
{
  "games": [
    {
      "title": "Game Title",
      "provider": "Game Provider",
      "category": "Game Category",
      "betOptions": ["Option1", "Option2"]
    }
  ]
}
```

### Additional Resources

For more information on how to integrate these endpoints into your system, please refer to the [API Documentation](#) or contact our support team for assistance.