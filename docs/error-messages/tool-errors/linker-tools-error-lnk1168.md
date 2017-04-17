---
title: "Erreur des outils &#201;diteur de liens LNK1168 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1168"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1168"
ms.assetid: 97ead151-fd99-46fe-9a1d-7e84dc0b8cc8
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Erreur des outils &#201;diteur de liens LNK1168
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible d'ouvrir nomfichier en écriture  
  
 L'éditeur de liens ne peut pas écrire dans `filename`.  Il est possible que le fichier soit utilisé et que son handle de fichier soit verrouillé par un autre processus. Il est possible également que vous ne disposiez pas de l'autorisation d'accès en écriture pour le fichier, ou pour le répertoire ou le partage réseau dans lequel il est situé.  Cette erreur résulte généralement d'une condition transitoire, par exemple, un verrou détenu par un antivirus, un processus d'indexation de recherche de fichiers ou un retard dans la libération d'un verrou détenu par le système de génération de [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)].  
  
 Pour résoudre ce problème, vérifiez que le handle de fichier de `filename` n'est pas verrouillé, et que vous disposez d'une autorisation d'accès en écriture pour le fichier.  S'il s'agit d'un exécutable, vérifiez qu'il n'est pas déjà en cours d'exécution.  
  
 Vous pouvez utiliser les utilitaires Windows SysInternals [Handle](http://technet.microsoft.com/sysinternals/bb896655.aspx) ou [Process Explorer](http://technet.microsoft.com/sysinternals/bb896653) pour déterminer le processus qui possède un verrou de descripteur de fichier sur `filename`.  Vous pouvez également utiliser Process Explorer pour libérer les verrous des handles de fichiers ouverts.  Pour plus d'informations sur l'utilisation de ces utilitaires, consultez les fichiers d'aide qui les accompagnent.  
  
 Si le fichier est verrouillé par un antivirus, vous pouvez résoudre ce problème en excluant les répertoires de sortie de génération de l'analyse automatique de l'antivirus.  Les scanners antivirus sont souvent déclenchés par la création de fichiers dans le système de fichiers. Par ailleurs, ils verrouillent les fichiers pendant l'analyse.  Consultez la documentation de votre antivirus pour plus d'informations sur la façon d'exclure des répertoires spécifiques de l'analyse.  
  
 Si le fichier est verrouillé par un service d'indexation de la recherche, vous pouvez résoudre ce problème en excluant les répertoires de sortie de génération de l'indexation automatique.  Consultez la documentation du service d'indexation pour plus d'informations.  Pour modifier le service d'indexation de la recherche de Windows, utilisez **Options d'indexation** dans le **Panneau de configuration** Windows.  Pour plus d'informations, consultez [Améliorer les recherches Windows à l'aide de l'index : Forum Aux Questions](http://windows.microsoft.com/en-us/windows/improve-windows-searches-using-index-faq#1TC=windows-7).  
  
 Si votre exécutable ne peut pas être remplacé par le processus de génération, cela signifie qu'il est peut\-être verrouillé par l'Explorateur de fichiers.  Si le service **Expérience d'application** est désactivé, l'Explorateur de fichiers peut verrouiller un handle de fichier exécutable pendant une durée prolongée.  Pour résoudre ce problème, exécutez **services.msc**, puis ouvrez la boîte de dialogue **Propriétés** du service **Expérience d'application**.  Modifiez le **Type de démarrage** en remplaçant **Désactivé** par **Manuel**.  
  
## Voir aussi  
 [Vous pouvez recevoir une « erreur PRJ0008 » ou un message d'erreur « Erreur fatale LNK1168 » lorsque vous essayez de générer une solution ou un projet ActiveX dans Visual C\+\+](http://support.microsoft.com/kb/308358)