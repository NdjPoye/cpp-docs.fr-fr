---
title: "Proc&#233;dure pas &#224; pas&#160;: compilation d&#39;un programme&#160;C++/CX sur la ligne de commande | Microsoft Docs"
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
ms.assetid: 626f5544-69ed-4736-83a9-f11389b371b2
caps.latest.revision: 8
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: compilation d&#39;un programme&#160;C++/CX sur la ligne de commande
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez créer des programmes Visual C\+\+ qui ciblent le Windows Runtime et les générer sur la ligne de commande.  Visual C\+\+ prend en charge les extensions de composant Visual C\+\+ \(C\+\+\/CX\), qui proposent des types et des opérateurs supplémentaires pour cibler le modèle de programmation Windows Runtime.  Vous pouvez utiliser C\+\+\/CX pour générer des applications pour Windows Phone 8.1, le Windows Store et le Bureau Windows.  Pour plus d'informations, consultez [Visite guidée de C\+\+\/CX](http://msdn.microsoft.com/magazine/dn166929.aspx) et [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md).  
  
 Dans cette procédure pas à pas, vous allez créer un programme C\+\+\/CX élémentaire à l'aide d'un éditeur de texte, puis le compiler sur la ligne de commande.  \(Vous pouvez utiliser votre propre programme C\+\+\/CX au lieu de taper le programme illustré, ou vous pouvez utiliser un exemple de code C\+\+\/CX tiré d'un autre article d'aide.  Cette technique est utile pour générer et tester des petits modules qui ne contiennent pas d'éléments d'interface utilisateur\).  
  
> [!NOTE]
>  Vous pouvez également utiliser l'IDE de Visual Studio pour compiler les programmes C\+\+\/CX.  Étant donné que l'IDE assure une prise en charge de la conception, du débogage, de l'émulation et du déploiement \(contrairement à la ligne de commande\), nous vous recommandons d'utiliser l'IDE pour générer des applications du Windows Store.  Pour plus d'informations, consultez [Create a basic C\+\+ Store app](http://msdn.microsoft.com/library/windows/apps/dn263168).  
  
## Composants requis  
 Vous devez posséder des notions de base du langage C\+\+.  
  
## Compilation d'un programme C\+\+\/CX  
 Pour activer la compilation pour du code C\+\+\/CX, vous devez utiliser l'option de compilateur [\/ZW](../build/reference/zw-windows-runtime-compilation.md).  Le compilateur Visual C\+\+ génère un fichier .exe qui cible le Windows Runtime, ainsi que des liens avec les bibliothèques requises.  
  
#### Pour compiler une application C\+\+\/CX sur la ligne de commande  
  
1.  Ouvrez une fenêtre d'**invite de commandes développeur**.  \(Dans la fenêtre **Démarrer**, ouvrez **Applications**.  Ouvrez le dossier **Visual Studio Tools** sous votre version de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], puis choisissez le raccourci **Invite de commandes développeur**.\) Pour plus d'informations sur la façon d'ouvrir une fenêtre d'invite de commandes, consultez [Définition du chemin d'accès et des variables d'environnement pour la génération à partir de la ligne de commande](../build/setting-the-path-and-environment-variables-for-command-line-builds.md).  
  
     Des informations d'identification d'administrateur peuvent être nécessaires pour compiler le code, selon la configuration et le système d'exploitation de l'ordinateur.  Pour exécuter la fenêtre d'invite de commandes en tant qu'administrateur, ouvrez le menu contextuel de l'**invite de commandes développeur**, puis choisissez **Exécuter en tant qu'administrateur**.  
  
2.  À l'invite de commandes, entrez **notepad basiccx.cpp**.  
  
     Lorsque vous êtes invité à créer un fichier, choisissez **Oui**.  
  
3.  Dans le Bloc\-notes, tapez les lignes suivantes :  
  
    ```cpp  
    using namespace Platform;  
  
    int main(Platform::Array<Platform::String^>^ args)  
    {  
        Platform::Details::Console::WriteLine("This is a C++/CX program.");  
    }  
  
    ```  
  
4.  Dans la barre de menus, choisissez **Fichier**, **Enregistrer**.  
  
     Vous venez de créer un fichier source Visual C\+\+ qui utilise l'espace de nom [Espace de noms de plateforme](../Topic/Platform%20namespace%20\(C++-CX\).md) du Windows Runtime.  
  
5.  À l'invite de commandes, entrez **cl \/EHsc \/ZW basiccx.cpp \/link \/SUBSYSTEM:CONSOLE**.  Le compilateur cl.exe compile le code source en un fichier .obj, puis exécute l'éditeur de liens pour générer un programme exécutable nommé basiccx.exe.  \(L'option de compilateur [\/EHsc](../build/reference/eh-exception-handling-model.md) spécifie le modèle de gestion des exceptions C\+\+, tandis que l'indicateur [\/link](../build/reference/link-pass-options-to-linker.md) spécifie une application de console.\)  
  
6.  Pour exécuter le programme basiccx.exe, à l'invite de commandes, entrez **basiccx**.  
  
     Le programme affiche ce texte puis se ferme :  
  
  **This is a C\+\+\/CX program.**  
  
## Voir aussi  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/fr-fr/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [Référence du langage C\+\+](../cpp/cpp-language-reference.md)   
 [Génération de programmes C\/C\+\+](../build/building-c-cpp-programs.md)   
 [Options du compilateur](../build/reference/compiler-options.md)