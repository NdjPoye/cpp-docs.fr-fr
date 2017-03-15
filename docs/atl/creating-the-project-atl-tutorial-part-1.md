---
title: "Cr&#233;ation du projet (Didacticiel ATL, Partie&#160;1) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
ms.assetid: f6b727d1-390a-4b27-b82f-daadcd9fc059
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Cr&#233;ation du projet (Didacticiel ATL, Partie&#160;1)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ce didacticiel vous démarrez étape par étape dans un projet ATL sans attributs qui crée un objet ActiveX qui affiche un polygone.  L'objet inclut des options pour permettre à l'utilisateur de modifier le nombre de côtés composant le polygone, et le code pour actualiser l'affichage.  
  
> [!NOTE]
>  ATL et MFC ne sont généralement pas pris en charge dans les éditions Express de Visual Studio.  
  
> [!NOTE]
>  Ce didacticiel crée le même code source que l'exemple polygon.  Si vous souhaitez éviter d'écrire du code source manuellement, vous pouvez le télécharger d' [Abrégé sur exemple polygon](../top/visual-cpp-samples.md).  Vous pouvez ensuite faire référence au code source polygon lorsque vous travaillez dans le didacticiel, ou l'utiliser pour rechercher des erreurs dans votre projet.  
  
### Pour créer le projet ATL initial à l'aide de l'Assistant Projet ATL  
  
1.  Dans l'environnement de développement Visual Studio, cliquez sur **Nouveau** dans le menu **Fichier**, puis cliquez sur **Projet**.  
  
2.  Cliquez sur le dossier **Projets Visual C\+\+** et sélectionnez **Projet ATL**.  
  
3.  Tapez `Polygone` comme nom du projet.  
  
     L'emplacement du code source aura comme valeur par défaut généralement à mes documents\\Visual Studio Projects, et un nouveau dossier est créé automatiquement.  
  
4.  Cliquez sur **OK** et Assistant Projet ATL s'ouvre.  
  
5.  Cliquez sur **Paramètres de l'application** pour consulter les options.  
  
6.  Lorsque vous créez un contrôle, et un contrôle doit être un serveur in\-process, permettent **Type d'application** en tant que DLL.  
  
7.  Conservez les autres options à leurs valeurs par défaut, puis cliquez sur **Terminer**.  
  
 L'Assistant Projet ATL crée le projet en générant plusieurs fichiers.  Vous pouvez afficher l'explorateur de ces fichiers dans l'en développant l'objet polygon.  Les fichiers sont répertoriés ci\-dessous.  
  
|Fichier|Description|  
|-------------|-----------------|  
|Polygon.cpp|Contient l'implémentation d' `DllMain`, d' `DllCanUnloadNow`, d' `DllGetClassObject`, d' `DllRegisterServer`, et d' `DllUnregisterServer`.  Contient également la table d'objets, qui est une liste d'objets ATL à votre projet.  C'est initialement vide.|  
|Polygon.def|Ce fichier de définition de module fournit à l'éditeur de liens des informations sur les exportations requises par votre DLL.|  
|Polygon.idl|Le fichier de langage de définition d'interface, qui décrit les interfaces spécifiques à vos objets.|  
|Polygon.rgs|Ce script de Registre contient des informations pour stocker la DLL de votre programme.|  
|Polygon.rc|Le fichier de ressources, qui contient initialement les informations de version et une chaîne contenant le nom du projet.|  
|Resource.h|Fichier d'en\-tête pour le fichier de ressources.|  
|Polygonps.def|Ce fichier de définition de module fournit à l'éditeur de liens des informations sur les exportations requises par le proxy et le code stub ces des appels du support technique entre les apartments.|  
|stdafx.cpp|Le fichier qui `#include` les fichiers d'implémentation ATL.|  
|stdafx.h|Le fichier qui `#include` les fichiers d'en\-tête ATL.|  
  
1.  Dans l'explorateur de solutions, cliquez avec le bouton droit sur le projet d' `Polygon` .  
  
2.  Dans le menu contextuel, cliquez sur **Propriétés**.  
  
3.  Cliquez sur **Éditeur de liens**.  Modifiez l'option **Par utilisateurRedirection** par **Oui**.  
  
4.  Cliquez sur **OK**.  
  
 Dans l'étape suivante, vous allez ajouter un contrôle à votre projet.  
  
 [Sur à l'étape 2](../atl/adding-a-control-atl-tutorial-part-2.md)  
  
## Voir aussi  
 [Didacticiel](../atl/active-template-library-atl-tutorial.md)