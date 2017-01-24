---
title: "/SUBSYSTEM (Sp&#233;cifier le sous-syst&#232;me) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/subsystem"
  - "VC.Project.VCLinkerTool.SubSystem"
  - "VC.Project.VCLinkerTool.SubSystemVersion"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SUBSYSTEM (option de l'éditeur de liens)"
  - "SUBSYSTEM (option de l'éditeur de liens)"
  - "-SUBSYSTEM (option de l'éditeur de liens)"
  - "spécifications du sous-système"
ms.assetid: d7b133cf-cf22-4da8-ab46-6552702c0b9b
caps.latest.revision: 25
caps.handback.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /SUBSYSTEM (Sp&#233;cifier le sous-syst&#232;me)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|  
            EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|NATIVE|  
            POSIX|WINDOWS)  
            [,major[.minor]]  
```  
  
 BOOT\_APPLICATION  
 Application qui s'exécute dans l'environnement à démarrage Windows.  Pour plus d'informations sur la création d'applications de démarrage, consultez [À propos de BCD](http://msdn.microsoft.com/library/windows/desktop/aa362639) \(en anglais\).  
  
 CONSOLE  
 Application en mode caractères Win32.  Le système d'exploitation fournit une console pour les applications console.  Si `main` ou `wmain` est défini pour le code natif, `int main(array<String ^> ^)` est défini pour le code managé ou si vous générez complètement l'application à l'aide de `/clr:safe`, CONSOLE est utilisé par défaut.  
  
 Interface EFI \(Extensible Firmware Interface\)  
 Les sous\-systèmes EFI\_\*.  Consultez la spécification EFI pour plus d'informations.  Par exemple, consultez le site Web d'Intel.  La version 1.0 est la version minimale et la version par défaut.  
  
 NATIVE  
 Pilotes en mode noyau pour Windows NT.  Cette option est généralement réservée aux composants du système Windows.  Si [\/DRIVER:WDM](../../build/reference/driver-windows-nt-kernel-mode-driver.md) est spécifié, NATIVE est la valeur par défaut.  
  
 POSIX  
 Application qui s'exécute avec le sous\-système POSIX dans Windows NT.  
  
 WINDOWS  
 L'application ne nécessite pas de console, car elle crée probablement ses propres fenêtres d'interaction avec l'utilisateur.  Si `WinMain` ou `wWinMain` est défini pour le code natif, ou si `WinMain(HISTANCE *, HINSTANCE *, char *, int)` ou `wWinMain(HINSTANCE *, HINSTANCE *, wchar_t *, int)` est défini pour le code managé, WINDOWS est la valeur par défaut.  
  
 `Major` et `minor` \(facultatives\)  
 Spécifie la version minimale requise pour le sous\-système.  Les arguments sont des chiffres décimaux compris entre 0 et 65 535.  Pour plus d'informations, consultez la section Notes.  Il n'existe aucune limite supérieure concernant les numéros de version.  
  
## Notes  
 L'option \/SUBSYSTEM spécifie l'environnement du fichier exécutable.  
  
 La sélection de cette option affecte le symbole de point d'entrée \(ou la fonction de point d'entrée\) que l'éditeur de liens sélectionne.  
  
 Les numéros facultatifs de versions minimales et par défaut `major` et `minor` pour les sous\-systèmes sont les suivants :  
  
|Sous\-système|Minimum|Valeur|  
|-------------------|-------------|------------|  
|BOOT\_APPLICATION|1.0|1.0|  
|CONSOLE|5.01 \(x86\) 5.02 \([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]\) 6.02 \(ARM\)|6.00 \(x86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]\) 6.02 \(ARM\)|  
|WINDOWS|5.01 \(x86\) 5.02 \([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]\) 6.02 \(ARM\)|6.00 \(x86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]\) 6.02 \(ARM\)|  
|NATIVE \(avec DRIVER:WDM\)|1.00 \(x86\) 1.10 \([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], ARM\)|1.00 \(x86\) 1.10 \([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], ARM\)|  
|NATIVE \(sans \/DRIVER:WDM\)|4.00 \(x86\) 5.02 \([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]\) 6.02 \(ARM\)|4.00 \(x86\) 5.02 \([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]\) 6.02 \(ARM\)|  
|POSIX|1.0|19.90|  
|EFI\_APPLICATION, EFI\_BOOT\_SERVICE\_DRIVER, EFI\_ROM, EFI\_RUNTIME\_DRIVER|1.0|1.0|  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le dossier Éditeur de liens.  
  
3.  Sélectionnez la page de propriétés **System**.  
  
4.  Modifiez la propriété `SubSystem`.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SubSystem%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)