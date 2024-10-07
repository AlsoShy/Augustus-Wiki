---
title: Killaura
description: Attacks enemies
---

<!-- <div style="border-left: 3px solid #EEBD53; background-color: #5C4C29; padding: 10px 15px; color: #F4E6C5; font-family: Arial, sans-serif; font-size: 14px; max-width: 600px; border-radius: 8px; box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);">
  <div style="display: flex; align-items: center; font-weight: bold; margin-bottom: 1px;">
    <span style="font-size: 20px; margin-right: 10px;">&#9888;</span>
    <span>Information</span>
  </div>
  <div>
    This document is in version in progress.
  </div>
</div> -->

Killaura is one of most important module in cheating. Killaura will automaticly aim at your enemy and attack. This module is essential to gain advantage over enemies. You may gain advantage by having greater reach, faster aim, better cps, autoblock or by ommiting some minecraft mechanics such as sprint-reset/reduction or attacking enemy through wall.

# Range

Range is one of most easiest sections of killaura to configure.

#### Min/Max PreAimRange

This setting defines when client should start aiming at enemy. It wont start attacking tho.
Min is when to start and Max when to stop.

#### Range

Range defines from how far you can hit someone. When the criteria is meet then client will start attacking enemy. PreAimRange should be higher than Range so it will be able to hit player the moment it can.

* Keep in mind that reach is not calculated by getting distance to enemy but to nearest point from player's perspective. Range 3 is default for vanila player.
* For anticheats that simulate game (Intave/Grim/Polar) this setting should be set to 3.

#### RangeMode

> *Simple*: Simply checks distance to player and compares with Range value. 

> *HazeRange*: Will increase reach while comboing your opponent by {HazeAdd} until {HazeMax}. 

> *Grim*: This mode is broken right now and causes Killaura to not attack at all. 

> *IntervalRange*: Not sure at the moment what it does. 

> *Dual*: Makes sometimes your reach higher {ExtendedRange} with chance {Chance Of Extended Range} % 

# Rotations

Rotations are very tricky to configure but are essential for not getting banned. Badly configured rotations can be detected if they act unhuman. Thats why this section is very detailed and has many diffrent setting to set. 

#### Yaw/Pitch Fov

This setting makes killaura not attack enemies that are far from you camera.

It takes diffrence from your rotation to angle of enemy. Then it compares Pitch/Vertical and Yaw/Horizontal diffrence in deegres. This setting is usefull if you dont want killaura to attack players you dont even see. It also makes it not very rapidly rotate to enemy.

### Min/Max Pitch/Yaw Speed/Acceleration

* This setting may be sometimes hidden due to some Randomize:Randomize modes

Main part of rotations. These settings specify by how much will your rotations come towards aiming point per tick. Pitch and Yaw calculations are seperated. For each axis (yaw/pitch) each tick speed is incremented by Acceleration and clamped by limit (Speed), then speed is added to your axis. If axis's target will change direction, acceleration will start accelerating in opposite direction. 

### Better Acceleration

Currently unknown what it does, try using this setting and watch if it improves killaura. It should work better.

### FixRotationMode

Currently unknown what it does, try using this setting and watch if it improves killaura. It may work best with OnlyWhenNeeded.

### Heurestics

This settings makes killaura aiming less detectable. Currently unknown how it works but might be worth testing if improves killaura. Try IntaveTest on IntaveAC, or Pattern1 (On other acs) and watch results.

### RotationMode

It determines killaura's aiming point. 

> Head: This mode will look at enemy's head. Most of client's use this method and may make your killaura more detectable, very basic and not recommended.

> BestHitVec: BestHitVec will target the closest part of enemy's hitbox, giving you the biggest advantage. Recommended.

> NearestHitVec: Will aim at the closest point to the player's cursor on the enemy's hitbox, then adjusting the aiming point only if the target no longer falls under the killaura's vector. Not that bad but BestHitVec is simply better.

Just set this to BestHitVec, no point at selecting other modes.

#### HitBoxPercentage Vertical/Horizontal

Defines percentage of hitbox on which rotations would be clamped. Towards center of hitbox.


## Randomize

Randomization of aim, very important.

### RandomType

This setting specifies which random distribution should be used.

> Random: Picks random number in specified range with linear distribution. Each number has equal chance.

> SecureRandom: Same as Random but doesn't use global random but private instance of random number generator. Linear uniform but numbers may be more evenly distributed.

> Gausian: Applies <a href="https://en.wikipedia.org/wiki/Normal_distribution" target="_blank">Gausian distribution</a> which makes numbers in middle of range be picked more often. 

> Intave: Applies unknown distribution for random numbers, may improve killaura on IntaveAC.

### Randomize

It specifies which randomization will get applied to player's rotation.

* Modes Noise, Turbo and Noise2 remove Min/Max Pitch/Yaw Speed/Acceleration overriding basic rotation.

> **None**: Dont apply any randomization.

> **Basic**: Randomly offsets aiming point by RandomStrength.

> **Doubled**: Same as Basic but may be more <i><b>special</b></i>.

> **OnlyRotation**: Works as Basic but only if player's head is rotating/aiming. If it already looks at aiming point it doesn't apply.

> **Hybrid**: Unknown what it does.

> **Polar**: Weird mode of randomization that might be very good. Oscilates pitch in yaw axis from above enemy's head to below his feet.

> **Circle**: Rotates in circle around aiming point. Radius becomes larger the further player is from enemy.

> **Advanced**: More sophisticated randomization, has many diffrent settings that i am not going to explain, if you are willing to use this mode you should see how diffrent settings change this mode. It basicly jumps around points in area defined by Circles{R=Radius} and exclusive for Circle{R=InnerRadius}, with Absolute and Relative distance from current offset.

> **Noise**: Randomly jumps around biased towards enemy. Overrides basic rotations and unpredictable. If you are willing to use this mode you should see how diffrent settings change this mode. Speed is how fast it will move, chances have weird/unexplained behaviour.

> **Turbo**: Mode made for IntaveAC with goal of improving basic rotations to work faster without getting detected. Designed for IntaveAC, but might be used for any anticheat. Depracted, see Noise2 (below).

> **Noise2**: Refresh of Noise rotation randomization with most humanly randomization. Made for IntaveAC and still undetected. Should work for every other anticheat including ones with better aim checks such as Polar, Matrix, Vulcan.

#### Turbo

##### Min/Max AimSpeed/Acceleration

Works same as basic rotation but without seperation for each axis (yaw/pitch);

##### Better Acceleration

Improves acceleration, unknown method. Keep around 0.3 - 0.5.

##### Scale

Not known at the moment what it does. Keep around 1 - 2.

##### Min/Max Target/Player Response

Ticks of prediction for tracking, not sure why these settings doesn't exist outside Turbo mode. Keep around (2-3) - (3-5), higher values for slower rotations (depending on anticheat).

#### Noise2

Works Similarly to Noise but with a little more settings

##### AimSpeed 

Base speed of rotation.

##### Deceleration Pre/Post

Some kind of Deceleration that is applied to some phase After(Post) and Before(Post). This phase is possibly rotating too target / correcting.

##### Min/Max Lookahead/Reaction

Specifies Limits of ticks for Lookahead (look how many ticks in target's predicted future position) and how fast to react for target going off our center of view.

##### Attention

¯\\_(ツ)_/¯

##### Min/Max prediction Innacuracy + Smoothness

Limits of how much prediction should be randomly offset and Smoothness of it (smoothness to not ranomly jiggle your cursor).

##### SuperCorrection

Random Correction of cursor to target, Min/Max delay beetwen corrections, Probability of it happenning and Additional Accuracy (no idea).

##### RotationOffset

Offset of target center to provide slight human-like innacuracy.

##### Additional Innacuracy

Make rotations extra innacurate to provide slight human-like innacuracy.

##### Orthogonal Scale / Aimpoint AngleDiff / HitVec Pitch Interpolation / Min/Max Rotation On Target / No Pitch/Yaw adjustment if bla bla bla / Ultimate TrashCode Bypas????? / Adapt Curve if Needed

Thanks god Esound is in repository maybe he will explain what the hell these do. Just try diffrent values and find which work the best.

##### Apply recorded mouse jitter

If Using Recorded Clicking jitter data might be store to be used there

### Tracking Accuracy/Randomization

Tracking is very usefull, it improves aiming speed. Tracking works by predicting where will enemy be in future and rotating to this point. Accuracy defines how accurate it is (?). And randomization by how much positions of player/enemy should be randomized. Just set randomization to like 5-20 and accuracy to 60-80.


### SmartAim

Improves killaura by aiming at small parts of target's hitbox, e.g. if half of the hitbox is behind a block, the client will aim at the visible part.

### SmartAimEntityCheck

An addition to SmartAim. Checks if there is any entity between you and killaura's target, and if true, will attempt to attack target without attacking entity.

### AdvancedRots

Probably improves something in aiming, unknown functionality, probably enable.

### Interpolation

Probably adds some sort of <a href="https://en.wikipedia.org/wiki/Linear_interpolation" target="_blank">Interpolation</a>, disable.

### LockView

Makes player's camera attached with player's rotation. If disabled player may look in diffrent direction than camera and when no longer needs to aim it will return to camera rotations. Doesn't change how killaura works, just where you look not player.

### AimThroughWalls

If disabled and player can't aim at point of enemy where it can be hit will stop looking at enemy. Enabled makes it always look at it.

#### AimThroughWallsRange

How close enemy should be to look at it through walls.

#### ThroughWalls

Decides if player should attack enemy through walls, might be detectable on some anticheats, may insta ban.

#### ThroughWallsRange

Range if player is hitting through wall.

### NoRotation

Disabled rotation. Super detectable and obvious, will autoban on every anticheat with hitbox check, 99% of anticheats have them. ENABLE.

## Clicking 

Basicly attacking. Autoblocks, perfecthit, cps settings, reduction, 1.9+ timings etc.

### ClickSettings

Describes how many clicks per second killaura can achive.

#### ClickMode

> **Basic**: Basic delay beetween each click in MS Min/Max Delay.

> **Deviation**: Basic cps Min/Max CPS, Can DoubleClick? and Multiplier of cps when player is not on ground.

> **Simple**: Deviation with Recalculate Delay basicly will randomize cps and use for next Min/Max Cps Recalculate Delay, no idea what Click Duty Cycle does set to 0.35 - 0.65 (default). There also is Extra Double Click Randomize, i dont have to explain what it does.

> **Recorded**: Will use pattern described in file. Can use MS Delay or Tick Delay. _/Air Multiplier that makes delay beetwen clicks larger.

> **Smart**: Uses SmartClicking and adds a lot of settings on top of it.

#### Smart ClickMode

##### Mode

> **Recommended**: Gives you *On Target*.

> **Overengineered**: Gives you *Hurttime n* from n 0 to 1.

##### Double| ClickMode

Esound will explain in future.

##### ConditionCPS

There are 5 main conditions which are:

> **On First Hit**: Met when firsthitting target.

> **On Wall**: Met when you are hitting a wall.

> **On Air**: Met when raycast missed and hit nothing.

*Recommended*:

> **On Target**: Met when raycast hit an entity which is your target, if its not your target it fallbacks to *On Air*.

*Overengineered*:

> **Hurttime n**: Met when raycast hit target and hurttime of it is equal to n.

##### Min/Max & NotInARow | CPS / CPSRecalculateTickDelay / DCPS / DCPSRecalculateTickDelay

> **Min/Max**: Lower / Upper bounds of limit:

> **Cps**: Clicks Per Second

> **DCPS**: Delta (diffrence beetwen each CPS) Clicks Per Second

> **NotInARow**: Will get another random if value is the same as last

> **RecalculateTickDelay**: Will use Same CPS until Recalculation happens which gets you new value. Happens every RecalculateTickDelay Ticks

#### Advanced ClickMode

##### Min/Max Cps/Delay

*Min*/*Max* Random Values for *Cps* / *Delay* values.

##### Spikes/Drops

> **Delay**: Delay beetwen each *spike*/*drop*.

> **Min/Max Duration**: Duration of each *spike*/*drop*.

> **Multi**: Cps Multiplier and Delay Divisor for *spike*/*drop*.

##### Reduce InAir / OnWall

> **Min/Max Multiplier**: Cps Multiplier and Delay Divisor for reduction.

> **Min/Max Recalculate Delay**: Recalculate Delay for each Multiplier.

##### Hurttimes to hit n

Toggle for each Hurttime n to attack on




### Interactions

You can find there packet based interactions of attacking/blocking.

#### AttackMode

How killaura will attack

> **Legit**: Will invoke clickMouse() function in minecraft code.

> **Packet**: Instead of asking minecraft to attack, sends packet C02PacketUseEntity with action ATTACK and entity your target.

> **Multi**: Will attack multiple entities in one tick. Switch killaura is way less undetected. This won't work on 90% of anticheats. Not worth to use anyway, switch killaura is almost the same.

#### BlockMode

This is the autoblock. Will significantly reduce incoming damage as you were blocking. Very important aspect of killaura.

None is simply no autoblock, Constant/2 is always blocking, Pre/Post are timings for when to block, UnblockOnHit/2 will "unblock on hit", Legit is legit autoblock (similiar effect as spamming both mouse buttons), and rest can't really be described.

* Killaura for blocking will work as you would just hold sword. This makes Noslow part of autoblock, without properly configured noslow autoblock may ban, slow you down.

#### SmartAutoblock

Unpredictable option for autoblock that makes it sometimes block sometimes not depending on situation.

#### InteractAutoblock

Normally autoblock for blocking/using item sends C08PacketPlayerBlockPlacement. This option replaces this packet send action with actual interaction. If player looks at chest it will interact with chest. Recommended for anticheats that simulate game.


#### OnlyRightClickBlock

Will autoblock only if player is holding right mouse button.

#### OnlyWhileSwingInProgess

Will autoblock only if player's item swing animation hasn't finished yet.

#### OnlyWhileHurt

Will autoblock only if player's hurttime (10 everytime you receive damage) is above 0 (you can receive damage now).

### PreHit

This settings make killaura attack and miss when enemy out of range.

### SmartPreHit

Not clear what this setting does, may improve PreHit.

### Min/Max PreHitRange

How far away enemy can be to prehit work.

### Min/Max PreHitFov

How far from camera can enemy be in deegres to prehit work.

### MissClick + Percentage

If MissClick is enabled, killaura will sometimes fail to hit enemy, and only swing item. Percentage defines how often this occurs.

### PerfectHit

Makes killaura only attack when enemy's hurttime equals to 0. This means killaura only attacks when enemy can receive damage.

### LongClick

This setting makes clicks more legitimate. When you are spamming your mouse to attack your enemy you not only press button down, but you also have to release it. This setting make killaura kind of simulating releasing mouse button.

### CritFix + PacketCheck

I am not 100% certain what it does but it may improve expirence on simulation based anticheats. Enable packet check.

### NoLoopHit

No idea what it does but as far as i know it may improve killaura a lot. Not sure what it does, and if its true.

### BreakBlocks

When killaura misses and would normally hit block nothing will happen. If this setting is enabled it will mine a block for short period of time. Makes killaura more legitimate, but disabling it may be better, no anticheat checks for that as far as i know.


### DoubleClickFirstHit

Makes first hit of killaura will always be a double click.

### ReduceCPSIfYouCantHitATarget

Will lower killaura cps if target is out of range.

### NoSwing

With this setting enabled killaura will no longer swing item when attacking. Super illegitimate every anticheat detects it. DISABLE.

### SlowDown

Applies minecraft standard movement motion reduction when attacking and sprinting. Neccesary for Polar/Intave, not for grim. Neccesary for sprint reset based MoreKB modes work. Enable if you feel you need it.

### CoolDown

For 1.9+ fighting you need to wait until your weapon cools down. Will wait for this to happen. Enable for 1.9+ versions.