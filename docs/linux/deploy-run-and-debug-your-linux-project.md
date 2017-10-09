---
title: "Déployer, exécuter et déboguer votre projet Linux | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-linux
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7084cdb-17b1-4960-b522-f84981bea879
author: BrianPeek
ms.author: brpeek
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 1f36435bbb8238fb6068e7b58f9142eda62bc28c
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---

# <a name="deploy-run-and-debug-your-project"></a>Déployer, exécuter et déboguer votre projet

Maintenant que vous avez créé le projet, vous devez vous connecter à votre ordinateur Linux, où le code sera compilé, exécuté et débogué.

1. Définissez l’architecture cible distante à l’aide de la liste déroulante standard dans Visual Studio comme indiqué : ![Remote Architecture](media/architecture.png) (Architecture distante)

Il existe plusieurs façons de manipuler et déboguer votre projet Linux.

* Les fonctionnalités classiques de Visual Studio, telles que les points d’arrêt, les fenêtres Espion et le pointage sur une variable, fonctionnant toutes comme prévu, vous pouvez déboguer comme vous le feriez normalement.
* Vous pouvez ouvrir une fenêtre de console Linux spéciale avec l’élément de menu **Debug > Linux Console** (Déboguer > Console Linux).

  ![Menu de console Linux](media/consolemenu.png)

  Cette console affiche toutes les sorties de console de l’ordinateur cible et prend les entrées pour les envoyer à l’ordinateur cible.

  ![Fenêtre de console Linux](media/consolewindow.png)

* Vous pouvez passer les arguments de ligne de commande à l’exécutable en utilisant l’élément **Arguments de programme** dans la page de propriétés **Débogage** du projet.
  
  ![Arguments de programme](media/settings_programarguments.png)

* GDB est utilisé pour déboguer les applications exécutées sur Linux.  Toutefois, il existe deux modes d’exécution différents qui peuvent être sélectionnés à partir de l’option **Mode de débogage** dans la page de propriétés **Débogage** du projet :

  ![Options GDB](media/settings_debugger.png)

  | Sélection | Description
  | --------- | ---
  | gdbserver | GDB s’exécute localement et se connecte à gdbserver, qui s’exécute sur le système distant.  Notez qu’il s’agit du seul mode que la fenêtre de console Linux prend en charge. 
  | gdb       | Le débogueur Visual Studio exécute GDB sur le système distant, ce qui est plus compatible si la version locale de GDB n’est pas compatible avec la version installée sur l’ordinateur cible

* Vous pouvez passer des options de débogueur spécifiques à GDB à l’aide de l’entrée **Commandes de débogueur supplémentaires**.  Par exemple, il est conseillé d’ignorer les signaux d’instruction non conforme (SIGILL).  Vous pouvez utiliser la commande **handle** pour y parvenir  en ajoutant le code suivant à l’entrée **Commandes de débogueur supplémentaires** comme indiqué ci-dessus :

  ```handle SIGILL nostop noprint```

