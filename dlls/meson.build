hl_server_src = [
    'aflock.cpp',
    'agrunt.cpp',
    'airtank.cpp',
    'animating.cpp',
    'animation.cpp',
    'apache.cpp',
    'barnacle.cpp',
    'barney.cpp',
    'bigmomma.cpp',
    'bloater.cpp',
    'bmodels.cpp',
    'bullsquid.cpp',
    'buttons.cpp',
    'cbase.cpp',
    'client.cpp',
    'combat.cpp',
    'controller.cpp',
    'crossbow.cpp',
    'crowbar.cpp',
    'defaultai.cpp',
    'doors.cpp',
    'effects.cpp',
    'egon.cpp',
    'explode.cpp',
    'flyingmonster.cpp',
    'func_break.cpp',
    'func_tank.cpp',
    'game.cpp',
    'gamerules.cpp',
    'gargantua.cpp',
    'gauss.cpp',
    'genericmonster.cpp',
    'ggrenade.cpp',
    'globals.cpp',
    'gman.cpp',
    'h_ai.cpp',
    'h_battery.cpp',
    'h_cine.cpp',
    'h_cycler.cpp',
    'h_export.cpp',
    'handgrenade.cpp',
    'hassassin.cpp',
    'headcrab.cpp',
    'healthkit.cpp',
    'hgrunt.cpp',
    'wpn_shared/hl_wpn_glock.cpp',
    'hornet.cpp',
    'hornetgun.cpp',
    'houndeye.cpp',
    'ichthyosaur.cpp',
    'islave.cpp',
    'items.cpp',
    'leech.cpp',
    'lights.cpp',
    'maprules.cpp',
    'monstermaker.cpp',
    'monsters.cpp',
    'monsterstate.cpp',
    'mortar.cpp',
    'mp5.cpp',
    'multiplay_gamerules.cpp',
    'nihilanth.cpp',
    'nodes.cpp',
    'observer.cpp',
    'osprey.cpp',
    'pathcorner.cpp',
    'plane.cpp',
    'plats.cpp',
    'player.cpp',
    '../pm_shared/pm_debug.c',
    '../pm_shared/pm_math.c',
    '../pm_shared/pm_shared.c',
    'python.cpp',
    'rat.cpp',
    'roach.cpp',
    'rpg.cpp',
    'satchel.cpp',
    'schedule.cpp',
    'scientist.cpp',
    'scripted.cpp',
    'shotgun.cpp',
    'singleplay_gamerules.cpp',
    'skill.cpp',
    'sound.cpp',
    'soundent.cpp',
    'spectator.cpp',
    'squadmonster.cpp',
    'squeakgrenade.cpp',
    'subs.cpp',
    'talkmonster.cpp',
    'teamplay_gamerules.cpp',
    'tempmonster.cpp',
    'tentacle.cpp',
    'triggers.cpp',
    'tripmine.cpp',
    'turret.cpp',
    'util.cpp',
    '../game_shared/voice_gamemgr.cpp',
    'weapons.cpp',
    'world.cpp',
    'xen.cpp',
    'zombie.cpp',
    'activity.h',
    'activitymap.h',
    'animation.h',
    'basemonster.h',
    'cbase.h',
    'cdll_dll.h',
    'client.h',
    'decals.h',
    'defaultai.h',
    'doors.h',
    'effects.h',
    '../engine/eiface.h',
    'enginecallback.h',
    'explode.h',
    'extdll.h',
    'flyingmonster.h',
    'func_break.h',
    'gamerules.h',
    'hornet.h',
    'items.h',
    'monsterevent.h',
    'monsters.h',
    'nodes.h',
    'plane.h',
    'player.h',
    '../pm_shared/pm_debug.h',
    '../pm_shared/pm_defs.h',
    '../pm_shared/pm_info.h',
    '../pm_shared/pm_materials.h',
    '../pm_shared/pm_movevars.h',
    '../pm_shared/pm_shared.h',
    'saverestore.h',
    'schedule.h',
    'scripted.h',
    'scriptevent.h',
    'skill.h',
    'soundent.h',
    'spectator.h',
    'squadmonster.h',
    'talkmonster.h',
    'teamplay_gamerules.h',
    'trains.h',
    'util.h',
    'vector.h',
    'weapons.h',
    'vehicle.cpp',
]

hl_server_defines = [
    '-DVOXEL',
    '-DQUAKE2',
    '-DCLIENT_WEAPONS',
    '-DVALVE_DLL',
]

hl_server_includes = include_directories([
    '.',
    '../engine',
    '../pm_shared',
    '../game_shared',
])

install_dir = '/valve/dlls' 
target_name = 'hl'
hl_server_lib = shared_library(target_name, hl_server_src,
    cpp_args            : hl_server_defines,
    c_args              : hl_server_defines,
    include_directories : [ hl_server_includes, goldsrc_includes ],
    vs_module_defs      : 'hl.def',
    install             : true,
    install_dir         : output_dir + install_dir,
)

hl_server_dep = declare_dependency(
    link_with           : [ hl_server_lib ],
)

cmd = join_paths(meson.current_build_dir(), '..\..\devtools\meson_set_outdir.bat')
cs = run_command(cmd, [target_name, meson.current_build_dir(), install_dir], check: false)
message(cs.stdout())