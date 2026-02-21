# Coding Standards & Conventions

## Naming Conventions
- **Scenes (.tscn)**: PascalCase (e.g., `PlayerCharacter.tscn`)
- **Scripts (.gd)**: snake_case (e.g., `player_controller.gd`)
- **Nodes**: PascalCase (consistent with Scene name)
- **Variables/Functions**: snake_case
- **Constants**: SCREAMING_SNAKE_CASE
- **Signals**: snake_case (e.g., `enemy_died`)

## Architecture
- **Composition over Inheritance**: Use smaller nodes/components for specific logic (Health, Stats) rather than deep inheritance trees.
- **Signals for Upward Communication**: Children emit signals; parents call methods on children.
- **Resources for Data**: All stats (speed, health, damage) should be stored in `.tres` files to allow for easy balancing and pooling.

## Performance (Bullet-Heaven Focus)
- **Object Pooling**: Mandatory for projectiles and common enemies.
- **Avoid `_process` for everything**: Use Signals or `State Machines` where possible.
- **Typed GDScript**: Always use static typing (`var x: int = 0`) for better performance and error catching.
