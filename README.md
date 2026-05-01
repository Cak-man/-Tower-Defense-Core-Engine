# Unity Tower Defense Core Systems

A comprehensive set of modular scripts for building Tower Defense or Automated Combat games in Unity. This system handles everything from AI navigation to projectile homing and spawner logic.

## ✨ Features
*   **Auto-Turret System:** Intelligent turret logic that detects enemies via triggers, rotates smoothly toward targets, and manages fire rates.
*   **Homing Projectiles:** Bullet script with target-tracking logic and damage application upon collision.
*   **NavMesh AI:** Enemy movement system that utilizes Unity's NavMesh for pathfinding and persistent target following.
*   **Flexible Spawner:** A randomized object spawner with configurable time intervals and physics force support.
*   **Health & Damage Framework:** A clean `EnemyHealth` system and trigger-based scene loaders for win/loss conditions.

## 🛠 Components & Setup

### 1. AutoShooter & Bullet
- Attach `AutoShooter` to your turret. Define the `TurretHead` for rotation and `FirePoint` for projectile instantiation.
- Projectiles use the `Bullet` script to track targets and apply damage to any entity with an `EnemyHealth` component.

### 2. Enemy AI (NavMesh)
- Attach `GoToTargetWithNavMesh` to enemies. 
- Ensure your scene is baked using Unity's **Navigation** window for the `NavMeshAgent` to function.

### 3. Spawner & Scene Management
- **RandomSpawner:** Perfect for waves. Drag your enemy prefabs into the array and set a spawn interval.
- **LoadSceneOnEnemyTrigger:** Use this on a "Base" or "Goal" object to trigger a Game Over or Victory scene when an enemy enters its range.

## 🕹 Logic Flow
1. **Spawn:** `RandomSpawner` creates an enemy at intervals.
2. **Move:** Enemy uses `NavMesh` to navigate toward the player's base.
3. **Detect:** Turret (`AutoShooter`) detects enemy tag in its trigger zone.
4. **Combat:** Turret rotates and fires `Bullet` objects that track the enemy.
5. **Outcome:** Enemy dies via `EnemyHealth` OR reaches the base, triggering `LoadSceneOnEnemyTrigger`.

## 📄 License
Open-source and free to use under the [MIT License](LICENSE).
