---
title: "Comment&#160;: incorporer un manifeste &#224; une application C/C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "incorporer des manifestes"
  - "makefiles, mettre à jour pour incorporer un manifeste"
  - "manifestes (C++)"
ms.assetid: ec0bac69-2fdc-466c-ab0d-710a22974e5d
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Comment&#160;: incorporer un manifeste &#224; une application C/C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il est recommandé que le manifeste d'une application \(ou d'une bibliothèque\) C\/C\+\+ soit incorporé à l'intérieur du fichier binaire final parce que cela garantit un comportement d'exécution correct dans la plupart des scénarios.  Par défaut, [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] tente d'incorporer le manifeste lorsqu'il génère un projet à partir de fichiers sources ; pour plus d'informations, consultez [Génération de manifeste dans Visual Studio](../build/manifest-generation-in-visual-studio.md).  Toutefois, si une application est générée à l'aide de nmake, certaines modifications doivent être apportées au makefile existant.  Cette section montre comment modifier des makefiles existants pour incorporer automatiquement le manifeste dans le fichier binaire final.  
  
## Deux approches  
 Il y a deux façons d'incorporer le manifeste à l'intérieur d'une application ou d'une bibliothèque.  
  
-   Si vous n'exécutez pas une génération incrémentielle, vous pouvez directement incorporer le manifeste à l'aide d'une ligne de commande similaire à la suivante comme étape post\-build :  
  
     **mt.exe –manifest MyApp.exe.manifest \-outputresource:MyApp.exe;1**  
  
     ou  
  
     **mt.exe –manifest MyLibrary.dll.manifest \-outputresource:MyLibrary.dll;2**  
  
     \(1 pour un EXE, 2 pour une DLL.\)  
  
-   Si vous exécutez une génération incrémentielle, la modification de la ressource comme illustré ici désactive la génération incrémentielle et provoque une régénération complète ; par conséquent, une approche différente doit être adoptée :  
  
    -   Liez le fichier binaire pour générer le fichier MyApp.exe.manifest.  
  
    -   Convertissez le manifeste en un fichier de ressources.  
  
    -   Procédez à une nouvelle liaison \(de façon incrémentielle\) pour incorporer la ressource manifeste dans le fichier binaire.  
  
 Les exemples suivants montrent comment modifier les makefiles pour incorporer les deux techniques.  
  
## Makefiles \(avant\)  
 Prenons le script nmake pour MyApp.exe, une application simple à partir d'un seul fichier :  
  
```  
# build MyApp.exe  
!if "$(DEBUG)" == "1"  
CPPFLAGS=$(CPPFLAGS) /MDd  
LFLAGS=$(LFLAGS) /INCREMENTAL  
!else  
CPPFLAGS=$(CPPFLAGS) /MD  
!endif  
  
MyApp.exe : MyApp.obj  
    link $** /out:$@ $(LFLAGS)  
  
MyApp.obj : MyApp.cpp  
  
clean :   
    del MyApp.obj MyApp.exe  
```  
  
 Si ce script est exécuté tel quel avec Visual C\+\+, il crée MyApp.exe avec succès.  Il crée également le fichier manifeste MyApp.exe.manifest externe, que le système d'exploitation utilisera pour charger des assemblys dépendants pendant l'exécution.  
  
 Le script nmake pour MyLibrary.dll paraît très similaire :  
  
```  
# build MyLibrary.dll  
!if "$(DEBUG)" == "1"  
CPPFLAGS=$(CPPFLAGS) /MDd  
LFLAGS=$(LFLAGS) /DLL /INCREMENTAL  
  
!else  
CPPFLAGS=$(CPPFLAGS) /MD  
LFLAGS=$(LFLAGS) /DLL  
  
!endif  
  
MyLibrary.dll : MyLibrary.obj  
    link $** /out:$@ $(LFLAGS)  
  
MyLibrary.obj : MyLibrary.cpp  
  
clean :   
    del MyLibrary.obj MyLibrary.dll  
```  
  
## Makefiles \(après\)  
 Pour effectuer la génération avec des manifestes incorporés, vous devez apporter quatre légères modifications aux fichiers makefile d'origine.  Pour le makefile MyApp.exe :  
  
```  
# build MyApp.exe  
!include makefile.inc  
#^^^^^^^^^^^^^^^^^^^^ Change #1. (Add full path if necessary.)  
  
!if "$(DEBUG)" == "1"  
CPPFLAGS=$(CPPFLAGS) /MDd  
LFLAGS=$(LFLAGS) /INCREMENTAL  
!else  
CPPFLAGS=$(CPPFLAGS) /MD  
!endif  
  
MyApp.exe : MyApp.obj  
    link $** /out:$@ $(LFLAGS)  
    $(_VC_MANIFEST_EMBED_EXE)  
#^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Change #2  
  
MyApp.obj : MyApp.cpp  
  
clean :   
    del MyApp.obj MyApp.exe  
    $(_VC_MANIFEST_CLEAN)  
#^^^^^^^^^^^^^^^^^^^^^^^^ Change #3  
  
!include makefile.targ.inc  
#^^^^^^^^^^^^^^^^^^^^^^^^^ Change #4. (Add full path if necessary.)  
```  
  
 Pour le makefile MyLibrary.dll :  
  
```  
# build MyLibrary.dll  
!include makefile.inc  
#^^^^^^^^^^^^^^^^^^^^ Change #1. (Add full path if necessary.)  
  
!if "$(DEBUG)" == "1"  
CPPFLAGS=$(CPPFLAGS) /MDd  
LFLAGS=$(LFLAGS) /DLL /INCREMENTAL  
  
!else  
CPPFLAGS=$(CPPFLAGS) /MD  
LFLAGS=$(LFLAGS) /DLL  
  
!endif  
  
MyLibrary.dll : MyLibrary.obj  
    link $** /out:$@ $(LFLAGS)  
    $(_VC_MANIFEST_EMBED_DLL)  
#^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Change #2.  
  
MyLibrary.obj : MyLibrary.cpp  
  
clean :   
    del MyLibrary.obj MyLibrary.dll  
    $(_VC_MANIFEST_CLEAN)  
#^^^^^^^^^^^^^^^^^^^^^^^^ Change #3.  
  
!include makefile.targ.inc  
#^^^^^^^^^^^^^^^^^^^^^^^^^ Change #4. (Add full path if necessary.)  
```  
  
 Les makefiles incluent désormais deux fichiers, makefile.inc et makefile.targ.inc, qui effectuent le véritable travail.  
  
 Créez makefile.inc et copiez\-y le code suivant :  
  
```  
# makefile.inc -- Include this file into existing makefile at the very top.  
  
# _VC_MANIFEST_INC specifies whether build is incremental (1 - incremental).  
# _VC_MANIFEST_BASENAME specifies name of a temporary resource file.  
  
!if "$(DEBUG)" == "1"  
CPPFLAGS=$(CPPFLAGS) /MDd  
LFLAGS=$(LFLAGS) /INCREMENTAL  
_VC_MANIFEST_INC=1  
_VC_MANIFEST_BASENAME=__VC90.Debug  
  
!else  
CPPFLAGS=$(CPPFLAGS) /MD  
_VC_MANIFEST_INC=0  
_VC_MANIFEST_BASENAME=__VC90  
  
!endif  
  
####################################################  
# Specifying name of temporary resource file used only in incremental builds:  
  
!if "$(_VC_MANIFEST_INC)" == "1"  
_VC_MANIFEST_AUTO_RES=$(_VC_MANIFEST_BASENAME).auto.res  
!else  
_VC_MANIFEST_AUTO_RES=  
!endif  
  
####################################################  
# _VC_MANIFEST_EMBED_EXE - command to embed manifest in EXE:  
  
!if "$(_VC_MANIFEST_INC)" == "1"  
  
#MT_SPECIAL_RETURN=1090650113  
#MT_SPECIAL_SWITCH=-notify_resource_update  
MT_SPECIAL_RETURN=0  
MT_SPECIAL_SWITCH=  
_VC_MANIFEST_EMBED_EXE= \  
if exist $@.manifest mt.exe -manifest $@.manifest -out:$(_VC_MANIFEST_BASENAME).auto.manifest $(MT_SPECIAL_SWITCH) & \  
if "%ERRORLEVEL%" == "$(MT_SPECIAL_RETURN)" \  
rc /r $(_VC_MANIFEST_BASENAME).auto.rc & \  
link $** /out:$@ $(LFLAGS)  
  
!else  
  
_VC_MANIFEST_EMBED_EXE= \  
if exist $@.manifest mt.exe -manifest $@.manifest -outputresource:$@;1  
  
!endif  
  
####################################################  
# _VC_MANIFEST_CLEAN - command to clean resources files generated temporarily:  
  
!if "$(_VC_MANIFEST_INC)" == "1"  
  
_VC_MANIFEST_CLEAN=-del $(_VC_MANIFEST_BASENAME).auto.res \  
    $(_VC_MANIFEST_BASENAME).auto.rc \  
    $(_VC_MANIFEST_BASENAME).auto.manifest  
  
!else  
  
_VC_MANIFEST_CLEAN=  
  
!endif  
  
# End of makefile.inc   
####################################################  
```  
  
 Maintenant créez makefile.targ.inc et copiez\-y le code suivant :  
  
```  
# makefile.targ.inc - include this at the very bottom of the existing makefile  
  
####################################################  
# Commands to generate initial empty manifest file and the RC file  
# that references it, and for generating the .res file:  
  
$(_VC_MANIFEST_BASENAME).auto.res : $(_VC_MANIFEST_BASENAME).auto.rc  
  
$(_VC_MANIFEST_BASENAME).auto.rc : $(_VC_MANIFEST_BASENAME).auto.manifest  
    type <<$@  
#include <winuser.h>  
1RT_MANIFEST"$(_VC_MANIFEST_BASENAME).auto.manifest"  
<< KEEP  
  
$(_VC_MANIFEST_BASENAME).auto.manifest :  
    type <<$@  
<?xml version='1.0' encoding='UTF-8' standalone='yes'?>  
<assembly xmlns='urn:schemas-microsoft-com:asm.v1' manifestVersion='1.0'>  
</assembly>  
<< KEEP  
  
# end of makefile.targ.inc  
```  
  
## Voir aussi  
 [Fonctionnement de la génération de manifestes pour les programmes C\/C\+\+](../build/understanding-manifest-generation-for-c-cpp-programs.md)