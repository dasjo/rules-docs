The Plug-in System of Drupal 8 provides a mechanism called (Plugin Derivates|https://www.drupal.org/node/1653226). This powerful concept allows a single plugin class to expose multiple plugins to the user interface.

In Rules, currently we use plugin derivates whenever dealing with entities: Instead of exposing a single "Create a new Entity" action, the user is presented with options like "Create a new Node", "Create a new Taxonomy Term" or "Create a new User".

According to our (Derivatives policy|https://www.drupal.org/node/2473169), we want to have derivatives whenever dealing with entity type based Actions or Conditions. Other cases might make sense, feel free to discuss them in the (policy issue|https://www.drupal.org/node/2473169).

A good reference implementation is the EntityCreate action: The (EntityCreate|https://github.com/fago/rules/blob/8.x-3.x/src/Plugin/Action/EntityCreate.php) action doesn't contain the context annotations, instead it references the (https://github.com/fago/rules/blob/8.x-3.x/src/Plugin/Action/EntityCreateDeriver.php|EntityCreateDeriver) who based on all entity types, provides derivatives. Also see the (related ticket|https://www.drupal.org/node/2409055).
