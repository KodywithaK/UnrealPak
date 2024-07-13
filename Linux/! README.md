# 0.Setup Unreal Engine

1.  `git clone --depth 1 --branch 4.27.2-release https://github.com/EpicGames/UnrealEngine.git`
    -   clones just the latest commit of UnrealEngine 4.27.2
2.  `cd ./UnrealEngine`[^1]

    1.  Replace "`./UnrealEngine/Engine/Build/`[Commit.gitdeps.xml](https://github.com/EpicGames/UnrealEngine/releases/download/4.27.2-release/Commit.gitdeps.xml)"[^2].
        -   fixes `Failed to download '...dependencies...'` in next step
    2.  `./setup.sh -exclude=WinRT -exclude=Mac -exclude=MacOS -exclude=MacOSX -exclude=osx -exclude=osx64 -exclude=osx32 -exclude=Android -exclude=IOS -exclude=TVOS -exclude=HTML5 -exclude=PS4 -exclude=XboxOne -exclude=Switch -exclude=Dingo`
        -   excludes unnecessary builds aka less space taken up.
        -   After successful run, `./Binaries/Linux/*` will be created
    3.  `./GenerateProjectFiles.sh`
        -   generates makefiles and CMakelists.txt
    4.  `make UnrealPak`
        -   makes `Unrealpak` and its dependencies in ~210s

# External Links

- [^1]: github.com/EpicGames/UnrealEngine [Linux Native compilation guide](https://github.com/EpicGames/UnrealEngine/blob/4.27.2-release/Engine/Build/BatchFiles/Linux/README.md)
- [^2]: Correct [Commit.gitdeps.xml](https://github.com/EpicGames/UnrealEngine/releases/download/4.27.2-release/Commit.gitdeps.xml)
