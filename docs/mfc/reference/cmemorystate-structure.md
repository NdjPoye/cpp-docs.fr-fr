---
title: Structure de CMemoryState | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMemoryState
dev_langs:
- C++
helpviewer_keywords:
- CMemoryState structure
- memory leaks, detecting
- detecting memory leaks
ms.assetid: 229d9de7-a6f3-4cc6-805b-5a9d9b1bfe1d
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 037c8f075a14346e3428c5e19bfda662c4f3c2b0
ms.lasthandoff: 02/24/2017

---
# <a name="cmemorystate-structure"></a>Structure de CMemoryState
Offre un moyen pratique pour détecter les fuites de mémoire dans votre programme.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
struct CMemoryState  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMemoryState::CMemoryState](#cmemorystate)|Construit une structure de classe qui contrôle les points de contrôle de mémoire.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMemoryState::Checkpoint](#checkpoint)|Obtient un instantané (point de contrôle) de l’état actuel de la mémoire.|  
|[CMemoryState::Difference](#difference)|Calcule la différence entre deux objets de type `CMemoryState`.|  
|[CMemoryState::DumpAllObjectsSince](#dumpallobjectssince)|Exporte un résumé de tous les objets actuellement alloués depuis un point de contrôle précédent.|  
|[CMemoryState::DumpStatistics](#dumpstatistics)|Imprime les statistiques d’allocation de mémoire pour un `CMemoryState` objet.|  
  
## <a name="remarks"></a>Notes  
 `CMemoryState`est une structure et ne dispose pas d’une classe de base.  
  
 Une « fuite de mémoire » se produit lors de la mémoire d’un objet est allouée sur le tas, mais pas libérée lorsqu’il n’est plus nécessaire. Les fuites de mémoire finalement conduire à des erreurs de mémoire insuffisante. Il existe plusieurs façons pour allouer et libérer la mémoire dans votre programme :  
  
-   À l’aide de la `malloc` /  **libre** famille de fonctions de la bibliothèque d’exécution.  
  
-   En utilisant les fonctions de gestion de mémoire API Windows, **LocalAlloc**/ **LocalFree** et **GlobalAlloc**/ **GlobalFree**.  
  
-   À l’aide de C++ **nouveau** et **supprimer** opérateurs.  
  
 Le `CMemoryState` diagnostics permettent uniquement de détecter la mémoire fuites dû à la mémoire allouée à l’aide de la **nouveau** opérateur n’est pas libéré à l’aide de **supprimer**. Les deux autres groupes de fonctions de gestion de la mémoire sont pour les programmes non-C++ et les combiner avec **nouveau** et **supprimer** dans le même programme n’est pas recommandée. Une macro supplémentaire, `DEBUG_NEW`, est fourni pour remplacer le **nouveau** opérateur lorsque vous avez besoin de fichiers et suivi des numéros de ligne des allocations de mémoire. `DEBUG_NEW`est utilisée chaque fois que vous utiliseriez normalement le **nouveau** opérateur.  
  
 Comme avec d’autres diagnostics, le `CMemoryState` diagnostics sont uniquement disponibles dans les versions debug de votre programme. Une version de débogage doit avoir le **_DEBUG** constante définie.  
  
 Si vous pensez que votre programme présente une fuite de mémoire, vous pouvez utiliser la `Checkpoint`, **différence**, et `DumpStatistics` fonctions pour détecter la différence entre l’état de la mémoire (objets alloués) à deux moments différents dans l’exécution du programme. Ces informations peuvent être utiles pour déterminer si une fonction nettoie tous les objets qu’il alloue.  
  
 Si simplement savoir où se produit le déséquilibre de l’allocation et la désallocation ne fournit pas suffisamment d’informations, vous pouvez utiliser la `DumpAllObjectsSince` pour vider tous les objets alloués depuis le précédent appel de fonction `Checkpoint`. Cette image illustre l’ordre d’allocation, le fichier source et la ligne où l’objet a été alloué (si vous utilisez `DEBUG_NEW` pour une allocation) et la dérivation de l’objet, son adresse et sa taille. `DumpAllObjectsSince`appelle également de chaque objet `Dump` fonction pour fournir des informations concernant son état actuel.  
  
 Pour plus d’informations sur l’utilisation de `CMemoryState` et autres diagnostics, consultez [le débogage des Applications MFC](/visualstudio/debugger/mfc-debugging-techniques).  
  
> [!NOTE]
>  Déclarations d’objets de type `CMemoryState` et les appels aux fonctions membres doivent être encadrées par des `#if defined(_DEBUG)/#endif` directives. Cela provoque des diagnostics de la mémoire être inclus uniquement dans les builds de votre programme de débogage.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `CMemoryState`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afx.h  
  
##  <a name="a-namecheckpointa--cmemorystatecheckpoint"></a><a name="checkpoint"></a>CMemoryState::Checkpoint  
 Prend un instantané récapitulatif de la mémoire et le stocke dans ce `CMemoryState` objet.  
  
```  
void Checkpoint();
```  
  
### <a name="remarks"></a>Remarques  
 Le `CMemoryState` les fonctions membres [différence](#difference) et [DumpAllObjectsSince](#dumpallobjectssince) utiliser ces données de capture instantanée.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de la [CMemoryState](#cmemorystate) constructeur.  
  
##  <a name="a-namecmemorystatea--cmemorystatecmemorystate"></a><a name="cmemorystate"></a>CMemoryState::CMemoryState  
 Construit un vide `CMemoryState` objet doit être rempli par le [Checkpoint](#checkpoint) ou [différence](#difference) fonction membre.  
  
```  
CMemoryState();
```  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_Utilities&#18;](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]  
  
##  <a name="a-namedifferencea--cmemorystatedifference"></a><a name="difference"></a>CMemoryState::Difference  
 Compare deux `CMemoryState` des objets, puis stocke la différence dans ce `CMemoryState` objet.  
  
```  
BOOL Difference(
    const CMemoryState& oldState,   
    const CMemoryState& newState);
```  
  
### <a name="parameters"></a>Paramètres  
 *oldState*  
 L’état de mémoire initial tel que défini par un `CMemoryState` point de contrôle.  
  
 *newState*  
 Le nouvel état de mémoire, tel que défini par un `CMemoryState` point de contrôle.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si les mémoire de deux États sont différents ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 [Point de contrôle](#checkpoint) doit être appelé pour chacun des deux paramètres d’état de la mémoire.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de la [CMemoryState](#cmemorystate) constructeur.  
  
##  <a name="a-namedumpallobjectssincea--cmemorystatedumpallobjectssince"></a><a name="dumpallobjectssince"></a>CMemoryState::DumpAllObjectsSince  
 Appelle le `Dump` (fonction) pour tous les objets d’un type dérivé de la classe `CObject` qui ont été alloués (et sont toujours allouées) depuis le dernier [Checkpoint](#checkpoint) appeler pour cette `CMemoryState` objet.  
  
```  
void DumpAllObjectsSince() const;

 
```  
  
### <a name="remarks"></a>Notes  
 Appel de `DumpAllObjectsSince` avec non initialisé `CMemoryState` dump d’objets à tous les objets actuellement en mémoire.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de la [CMemoryState](#cmemorystate) constructeur.  
  
##  <a name="a-namedumpstatisticsa--cmemorystatedumpstatistics"></a><a name="dumpstatistics"></a>CMemoryState::DumpStatistics  
 Imprime un rapport de statistiques de mémoire concise à partir un `CMemoryState` objet rempli par le [différence](#difference) fonction membre.  
  
```  
void DumpStatistics() const;

 
```  
  
### <a name="remarks"></a>Remarques  
 L’état qui est imprimé sur la [afxDump](http://msdn.microsoft.com/library/4b3cfa3f-fb75-456a-9d99-a5601acbcb11) périphérique, affiche les informations suivantes :  
  
 Un exemple de rapport fournit des informations sur le nombre (ou montant) de :  
  
-   nombre de blocs libres  
  
-   blocs Normal  
  
-   Blocs CRT  
  
-   Ignorer les blocs  
  
-   blocs clients  
  
-   mémoire maximale utilisée par le programme à tout moment (en octets)  
  
-   quantité totale de mémoire actuellement utilisée par le programme (en octets)  
  
 Les blocs libres sont le nombre de blocs dont la désallocation est différée si `afxMemDF` a **delayFreeMemDF**. Pour plus d’informations, consultez [afxMemDF](diagnostic-services.md#afxmemdf), dans la section « MFC Macros et objet Globals ». Consultez la page [Types de blocs sur le tas de débogage](http://msdn.microsoft.com/en-us/db2e7f62-0679-4b39-a23f-26f2c2f407c5) pour bloquer les plus d’informations sur ces types.  
  
### <a name="example"></a>Exemple  
  Le code suivant doit être placé dans *NomProjet*App.cpp. Définissez les variables globales suivantes :  
  
 [!code-cpp[NVC_MFC_Utilities numéro&40;](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]  
  
 Dans le `InitInstance` fonctionne, ajoutez la ligne :  
  
 [!code-cpp[# NVC_MFC_Utilities&41;](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]  
  
 Ajoutez un gestionnaire pour le `ExitInstance` la fonction et utilisez le code suivant :  
  
 [!code-cpp[NVC_MFC_Utilities&#42;](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]  
  
 Vous pouvez maintenant exécuter le programme en mode débogage pour voir le résultat de la `DumpStatistics` (fonction).  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)




