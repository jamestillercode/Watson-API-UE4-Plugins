# Watson API UE4 Plugins

These plugins are more or less based on the .NET/Java plugins that IBM maintains internally. There's a Unity plugin too maintained by them, but I use Unreal so this is the same thing but for that. The initial version of this plugin is going to use Unreal's VaRest plugin, but we'll migrate to a internally maintained service backend based on libcurl once the initial services are up and running, in order to reduce dependencies. VaRest is free, Open Source, and super awesome, but we want to be self-sufficient to reduce unintended variance. 

# FAQ

### Why is this built in Blueprints, isn't C++ all the rage?
There are a couple of reasons we're leaning on Blueprints rather than C++. For one, v0.1 of these plugins is being built with the very easy to use VaRest plugin, which is Blueprint facing. While we're moving to our own Rest-like connection at some point, there's two major goals that we have from this plugin: 1) Extensibility. Watson has a knack for changing on the fly, but more importantly you can also add your own output fields in Conversation, and build custom models for Discovery/Natural Language Understanding. Game Designers should feel comfortable adding a field on the fly, which means Blueprints. 2) Unreal's C++ is kind of wonky at the moment in time that this project is starting. They're breaking up the header files, but also, Macros are *everywhere* making it a pain to debug if you get a strange error. Compile times also aren't the greatest yet. These things are definitely improving with each successive version release, but since Epic seems to be pushing users towards BP anyway, we're going to do that.

### I don't see a Watson service I need, where is it?
The plan is to implement every Watson API service that's available in their public API. Beyond that, you'll have to implement it yourself. If there's a public API that's not here yet, it's on the way!
