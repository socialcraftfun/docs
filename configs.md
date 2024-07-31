# Конфиги сервера

Эта статья предоставляет обзор основных настроек серверов и вспомогательных функций. Здесь вы найдете ключевые параметры, необходимые для оптимальной работы серверов, а также дополнительные функции, способствующие эффективности и безопасности серверной инфраструктуры.

### Хостинг

**Hosting-Minecraft** Тариф [TRIPLE CORE](https://my.hosting-minecraft.pro/aff.php?aff=533)
- **CPU**: AMD Ryzen 9 3900 4300МГц
- **RAM**: 8 ГБ DDR4
- **SSD**: 100GB NVMe

### Границы миров

- Верхний мир - 7266
- Нижний мир - неограничен
- Мир края - неограничен

### Конфигурация


Для настройки спавна мобов мы используем следующую [таблицу](https://docs.google.com/spreadsheets/d/1wAU1GMSBJlocaJhvlkiILDBR98krKm2Q5hVqo-vtXMo/edit?usp=sharing), основанную на проверенных гайдах:

**Гайды:**
- [Paper Chan's Little Guide to Minecraft Server Optimization!](https://paper-chan.moe/paper-optimization/#mobspawn)
- [Плохой спавн мобов в темноте, и варианты решения проблемы.](https://www.minecraft-moscow.ru/threads/3787/)

#### gamerule

- playersSleepingPercentage: 50

#### server.properties


Подробнее о каждом параметре: [https://docs.papermc.io/paper/reference/server-properties](https://docs.papermc.io/paper/reference/server-properties)

```properties
difficulty=hard
view-distance=7
simulation-distance=7
```

#### bukkit.yml


Подробнее о каждом параметре: [https://docs.papermc.io/paper/reference/bukkit-configuration](https://docs.papermc.io/paper/reference/bukkit-configuration)

```yaml
spawn-limits: # Количество мобов на игрока
    monsters: 60 # Монстры 
    animals: 10 # Животные
    water-animals: 5 # Водные животные (Дельфины, спруты, ...) 
    water-ambient: 10 # Водные животные (Рыбы)
    water-underground-creature: 5 # Водные подземные животные (Светящийся спрут)
    axolotls: 5 # Аксолотль 
    ambient: 5 # Окружение (Летучие мыши)
ticks-per: # Количество тиков на спавн моба [20 тиков = 1 сек]
    monster-spawns: 2 # 100 мс
    animal-spawns: 400 # 20 сек
    water-spawns: 100 # 5 сек
    water-ambient-spawns: 100 # 5 сек
    water-underground-creature-spawns: 100 # 5 сек
    axolotl-spawns: 100 # 5 сек
    ambient-spawns: 100 # 5 сек
```

#### spigot.yml

Подробнее о каждом параметре: [https://docs.papermc.io/paper/reference/spigot-configuration](https://docs.papermc.io/paper/reference/spigot-configuration)

```yaml
item-despawn-rate: 6000 # 5 мин
ticks-per:
     hopper-transfer: 8
     hopper-check: 1
mob-spawn-range: 6
entity-activation-range:
    ignore-spectators: false
    animals: 32
    monsters: 32
    raiders: 64
    misc: 16
    water: 16
    villagers: 32
    flying-monsters: 32
    villagers-work-immunity-after: 100
    villagers-work-immunity-for: 20
    villagers-active-for-panic: true
    tick-inactive-villagers: true
    wake-up-inactive:
        animals-max-per-tick: 4
        animals-every: 1200
        animals-for: 100
        monsters-max-per-tick: 8
        monsters-every: 400
        monsters-for: 100
        villagers-max-per-tick: 4
        villagers-every: 600
        villagers-for: 100
        flying-monsters-max-per-tick: 8
        flying-monsters-every: 200
        flying-monsters-for: 100
```

#### paper-global.yml

Подробнее о каждом параметре: [https://docs.papermc.io/paper/reference/global-configuration](https://docs.papermc.io/paper/reference/global-configuration)

```yaml
unsupported-settings:
    allow-headless-pistons: true
    allow-permanent-block-break-exploits: true
    allow-piston-duplication: true
    allow-tripwire-disarming-exploits: false
    allow-unsafe-end-portal-teleportation: false
    perform-username-validation: true
    skip-vanilla-damage-tick-when-shield-blocked: false
```

#### paper-world-defaults.yml

Подробнее о каждом параметре: [https://docs.papermc.io/paper/reference/world-configuration](https://docs.papermc.io/paper/reference/world-configuration)

```yaml
despawn-ranges:
    hard: 96
    soft: 32
lootables:
    auto-replenish: true
    max-refills: -1
    refresh-max: 2d
    refresh-min: 12h
    reset-seed-on-fill: true
    restrict-player-reloot: false
    restrict-player-reloot-time: disabled
pillager-patrols:
    disable: false
    spawn-chance: 0.2
    spawn-delay:
        per-player: true
        ticks: 12000
    start:
        day: 5
        per-player: true
```
