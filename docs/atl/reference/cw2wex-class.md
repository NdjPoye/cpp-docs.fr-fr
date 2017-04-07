---
title: Classe de CW2WEX | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CW2WEX
- ATLCONV/ATL::CW2WEX
- ATLCONV/ATL::CW2WEX::CW2WEX
- ATLCONV/ATL::CW2WEX::m_psz
- ATLCONV/ATL::CW2WEX::m_szBuffer
dev_langs:
- C++
helpviewer_keywords:
- CW2WEX class
ms.assetid: 46262e56-e0d2-41fe-855b-0b67ecc8fcd7
caps.latest.revision: 20
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 9382f8404c1469b3f847500f35ab26499b6579bc
ms.lasthandoff: 02/24/2017

---
# <a name="cw2wex-class"></a>CW2WEX (classe)
Cette classe est utilisée par les macros de conversion de chaînes `CW2TEX` et `CT2WEX`et le typedef `CW2W`.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <int t_nBufferLength = 128>  
class CW2WEX
```  
  
#### <a name="parameters"></a>Paramètres  
 `t_nBufferLength`  
 La taille de la mémoire tampon utilisée dans le processus de traduction. La longueur par défaut est 128 octets.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CW2WEX::CW2WEX](#cw2wex)|Constructeur.|  
|[CW2WEX :: ~ CW2WEX](#dtor)|Destructeur.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CW2WEX::operator LPWSTR](#operator_lpwstr)|Opérateur de conversion.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CW2WEX::m_psz](#m_psz)|Le membre de données qui stocke la chaîne source.|  
|[CW2WEX::m_szBuffer](#m_szbuffer)|La mémoire tampon statique, utilisé pour stocker la chaîne convertie.|  
  
## <a name="remarks"></a>Remarques  
 À moins que des fonctionnalités supplémentaires sont requises, utilisez `CW2TEX`, `CT2WEX`, ou `CW2W` dans votre code.  
  
 Cette classe contient une mémoire tampon de taille fixe statique qui est utilisé pour stocker le résultat de la conversion. Si le résultat est trop grand pour tenir dans la mémoire tampon statique, la classe alloue de la mémoire avec `malloc` et libère la mémoire quand l'objet passe en dehors de l'étendue. Cela garantit que, contrairement au texte de macros de conversion disponibles dans les versions précédentes d’ATL, cette classe est sûr à utiliser dans des boucles et qu’il ne dépassement de la pile.  
  
 Si la classe tente d’allouer de la mémoire sur le tas et échoue, il appellera `AtlThrow` avec un argument de **E_OUTOFMEMORY**.  
  
 Par défaut, les classes de conversion ATL et les macros utilisent la page de codes ANSI du thread actuel pour la conversion.  
  
 Les macros suivantes sont basées sur cette classe :  
  
- `CW2TEX`  
  
- `CT2WEX`  
  
 Le typedef suivant est basé sur cette classe :  
  
- `CW2W`  
  
 Pour une description de ces macros de conversion de texte, consultez [Macros de Conversion de chaînes de MFC et ATL](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863).  
  
## <a name="example"></a>Exemple  
 Consultez la page [ATL et MFC Macros de Conversion de chaînes](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863) pour obtenir un exemple d’utilisation de ces macros de conversion de chaînes.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlconv.h  
  
##  <a name="cw2wex"></a>CW2WEX::CW2WEX  
 Constructeur.  
  
```
CW2WEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2WEX( LPCWSTR  psz) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `psz`  
 La chaîne de texte à convertir.  
  
 `nCodePage`  
 La page de codes. Pas utilisé dans cette classe.  
  
### <a name="remarks"></a>Remarques  
 Crée la mémoire tampon requise pour la traduction.  
  
##  <a name="dtor"></a>CW2WEX :: ~ CW2WEX  
 Le destructeur...  
  
```
~CW2WEX() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Libère la mémoire tampon allouée.  
  
##  <a name="m_psz"></a>CW2WEX::m_psz  
 Le membre de données qui stocke la chaîne source.  
  
```
LPWSTR m_psz;
```  
  
##  <a name="m_szbuffer"></a>CW2WEX::m_szBuffer  
 La mémoire tampon statique, utilisé pour stocker la chaîne convertie.  
  
```
wchar_t m_szBuffer[t_nBufferLength];
```  
  
##  <a name="operator_lpwstr"></a>CW2WEX::operator LPWSTR  
 Opérateur de cast.  
  
```  
operator LPWSTR() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la chaîne de texte en tant que type `LPWSTR`.  
  
## <a name="see-also"></a>Voir aussi  
 [CA2AEX (classe)](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX (classe)](../../atl/reference/ca2caex-class.md)   
 [CA2WEX (classe)](../../atl/reference/ca2wex-class.md)   
 [CW2AEX (classe)](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX (classe)](../../atl/reference/cw2cwex-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

