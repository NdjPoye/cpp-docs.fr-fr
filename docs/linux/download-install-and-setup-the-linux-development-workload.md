---
title: "Télécharger, installer et configurer la charge de travail Linux | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-linux
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e11b40b2-f3a4-4f06-b788-73334d58dfd9
author: BrianPeek
ms.author: brpeek
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 338f1bd87dbaaf4caf6a788cd45b3d011bbf40f0
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---

# <a name="download-install-and-setup-the-linux-workload"></a>Télécharger, installer et configurer la charge de travail Linux

## <a name="visual-studio-setup"></a>Installation de Visual Studio
1. Démarrez le programme d’installation de Visual Studio et sélectionnez la charge de travail **Développement Linux en C++**.

   ![Extension de Visual C++ pour le développement Linux](media/linuxworkload.png)

2. Cliquez sur **Installer** pour continuer l’installation.

## <a name="linux-setup"></a>Configuration de Linux
**openssh-server**, **g++**, **gdb** et **gdbserver** doivent être installés sur l’ordinateur Linux cible et le démon ssh doit être en cours d’exécution.  Si ces éléments ne sont pas déjà présents, vous pouvez les installer comme suit :
 
1. À l’invite de commandes du shell sur votre ordinateur Linux, exécutez :

   `sudo apt-get install openssh-server g++ gdb gdbserver`

   Vous pouvez être invité à indiquer votre mot de passe racine en raison de la commande sudo.  Dans ce cas, entrez-la et continuez.  Quand vous avez terminé, ces outils et services sont installés.

1. Vérifiez que le service ssh est en cours d’exécution sur votre ordinateur Linux en exécutant :

   `sudo service ssh start`
   
   Vous démarrez ainsi le service qui s’exécute en arrière-plan, prêt à accepter des connexions.

