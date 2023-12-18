# XTools 0.5

Hello this is XTools a framework for unity made by game developers for game developers.
It are maked from 2 parts The libs and The Mods. In this firs version it have 2 Mods.
UMOD a alternative to FMOD. UMOD are a very lightweight audio framework for provide
a fast and easy to use audio framework.Another mod are SMOD(SaveMOD) a framework
for help whit DataSaving, it are another alternative to EasySave3. It suport save in
differents formats like XML(The best in our opinion because it support saving of Vectors whitouth using a Serializable one
alternative), Binary, JSON. And the last WFCMod(WaveFunctionCollapseMod), it are only a implementatio
of the algorithm

### Documentation

> [!TIP]
> Remember the docs are in beta

## UMOD

This is the part of the framework dedicated to make good sound. It are subject to changes in the future
like a plugin search system and more. It only has two components AudioPlayer and UAudioWorker.

> [!TIP]
> We recomend only use AudioPlayer because
> UAudioWorker are legacy and dont are going
> to recive any update

For use AudioPlayer are that easy as make you audio state like: walk, fall, run, etc
and the code implementation are more easy. You only need to know to functions.
SetAudioState(int state) and  Play(), Pause() whit this you can make you own implementation
like this

>void OnPlayerFall() {
>  player.SetAudioState(1)
>  player.Play()
>}

## SaveMod and FastSaver

Fast saver are a form to save the data more easy
this can be implemented by a few lines of code like this:

>void Save() {
>saver.Save<SerializableVector3>("playerpos", player.transform.position);
>saver.SaveFile("MySave", SaveType.Binary)
>}
>
>void Load() {
>saver.LoadFile("playerpos", SaveType.Binary)
>player.transform.position = saver.Load<Vector3>("playerpos");
>}
>

## WFCMod

Only know that is you call the function BuildWFC() of a WFCBuilder it will make the WFC
