---
title: Redistribution de contrôles ActiveX Visual C++ | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], redistributing
- controls [C++], distributing
ms.assetid: eefbb7e4-d28c-4c35-98bf-d9540cfaae83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b770bbacca06c6edfb3b9b4eda53fc7be8a7ae0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="redistributing-visual-c-activex-controls"></a>Redistribution de contrôles ActiveX Visual C++
Visual C++ 6.0 fournit des contrôles ActiveX que vous pouvez utiliser dans les applications que vous redistribuez ensuite. Ces contrôles ne sont plus inclus dans Visual C++. Par les contrats de licence de Visual C++ 6.0, vous pouvez redistribuer ces contrôles avec les applications développées dans Visual C++.  
  
> [!NOTE]
>  Visual C++ 6.0 n’est plus pris en charge par Microsoft.  
  
 Pour obtenir la liste des contrôles ActiveX de Visual C++ 6.0 redistribuables, consultez Common\Redist\Redist.txt sur le disque 1 du CD-ROM du produit Visual C++ 6.0.  
  
 Lorsque vous distribuez des applications, vous devez installer et inscrire le fichier .ocx du contrôle ActiveX (à l’aide de Regsvr32.exe). En outre, il se peut que vous devez vous assurer que l’ordinateur cible dispose des versions actuelles des fichiers système suivants (un astérisque indique que le fichier doit être inscrit) :  
  
-   Asycfilt.dll  
  
-   Comcat.dll *  
  
-   Oleaut32.dll *  
  
-   OLEPRO32.dll *  
  
-   Stdole2.tlb  
  
 Si ces DLL n’est pas disponibles sur le système cible, vous devez obtenir les mises à jour avec le mécanisme recommandé pour la mise à jour du système d’exploitation correspondant. Vous pouvez télécharger les derniers service packs pour les systèmes d’exploitation Windows à partir de [ http://windowsupdate.microsoft.com ](http://windowsupdate.microsoft.com).  
  
 Si votre application utilise un des contrôles ActiveX qui se connecte à une base de données, vous devez disposer du Microsoft Data Access composants (MDAC) installée sur le système cible. Pour plus d’informations, consultez [redistribution de fichiers de prise en charge de base de données](../ide/redistributing-database-support-files.md).  
  
 Lorsque vous utilisez un contrôle ActiveX qui se connecte à une base de données, vous devez également répliquer le nom de source de données sur l’ordinateur cible. Vous pouvez procéder par programme avec des fonctions telles que `ConfigDSN`.  
  
 Certains contrôles ActiveX redistribuables ont des dépendances supplémentaires. Pour chaque fichier .ocx du dossier Os\System sur le CD-ROM du produit Visual C++ 6.0, il existe également un fichier .dep. Pour chaque fichier .ocx que vous souhaitez redistribuer, recherchez une ou plusieurs entrées USES dans le fichier .dep correspondant. Si un fichier est répertorié, vous devez vous assurer que le fichier se trouve sur l’ordinateur cible. Toutes les DLL prenant directement en charge un fichier .ocx doivent être inscrits. (Pour Regsvr32.exe réussisse, l’ordinateur cible doit d’abord inclure toutes les DLL chargées statiquement par le contrôle.) En outre, si une DLL qui est répertoriée en tant que dépendance a également un fichier .dep dans le dossier Os\System sur le CD-ROM Visual C++ 6.0, vous devez également rechercher les entrées USES dans ce fichier .dep.  
  
## <a name="see-also"></a>Voir aussi  
 [Redistribution des fichiers Visual C++](../ide/redistributing-visual-cpp-files.md)