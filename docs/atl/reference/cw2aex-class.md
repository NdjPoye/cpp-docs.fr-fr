---
title: Classe de CW2AEX | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CW2AEX
- ATLCONV/ATL::CW2AEX
- ATLCONV/ATL::CW2AEX::CW2AEX
- ATLCONV/ATL::CW2AEX::m_psz
- ATLCONV/ATL::CW2AEX::m_szBuffer
dev_langs:
- C++
helpviewer_keywords:
- CW2AEX class
ms.assetid: 44dc2cf5-dd30-440b-a9b9-b21b43f49843
caps.latest.revision: 21
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
ms.openlocfilehash: 8bf433224396f54b81fb5310ec29dfed213c6855
ms.lasthandoff: 02/24/2017

---
# <a name="cw2aex-class"></a>CW2AEX (classe)
Cette classe est utilisée par les macros de conversion de chaînes `CT2AEX`, `CW2TEX`, `CW2CTEX`, et `CT2CAEX`et le typedef **CW2A**.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<int t_nBufferLength = 128>  
class CW2AEX
```  
  
#### <a name="parameters"></a>Paramètres  
 `t_nBufferLength`  
 La taille de la mémoire tampon utilisée dans le processus de traduction. La longueur par défaut est 128 octets.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CW2AEX::CW2AEX](#cw2aex)|Constructeur.|  
|[CW2AEX :: ~ CW2AEX](#dtor)|Destructeur.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CW2AEX::operator LPSTR](#operator_lpstr)|Opérateur de conversion.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CW2AEX::m_psz](#m_psz)|Le membre de données qui stocke la chaîne source.|  
|[CW2AEX::m_szBuffer](#m_szbuffer)|La mémoire tampon statique, utilisé pour stocker la chaîne convertie.|  
  
## <a name="remarks"></a>Notes  
 À moins que des fonctionnalités supplémentaires sont requises, utilisez `CT2AEX`, `CW2TEX`, `CW2CTEX`, `CT2CAEX`, ou **CW2A** dans votre code.  
  
 Cette classe contient une mémoire tampon de taille fixe statique qui est utilisé pour stocker le résultat de la conversion. Si le résultat est trop grand pour tenir dans la mémoire tampon statique, la classe alloue de la mémoire avec `malloc` et libère la mémoire quand l'objet passe en dehors de l'étendue. Cela garantit que, contrairement au texte de macros de conversion disponibles dans les versions précédentes d’ATL, cette classe est sûr à utiliser dans des boucles et qu’il ne dépassement de la pile.  
  
 Si la classe tente d’allouer de la mémoire sur le tas et échoue, il appellera `AtlThrow` avec un argument de **E_OUTOFMEMORY**.  
  
 Par défaut, les classes de conversion ATL et les macros utilisent la page de codes ANSI du thread actuel pour la conversion. Si vous souhaitez substituer ce comportement pour une conversion spécifique, spécifiez la page de codes comme second paramètre au constructeur de la classe.  
  
 Les macros suivantes sont basées sur cette classe :  
  
- `CT2AEX`  
  
- `CW2TEX`  
  
- `CW2CTEX`  
  
- `CT2CAEX`  
  
 Le typedef suivant est basé sur cette classe :  
  
- **CW2A**  
  
 Pour une description de ces macros de conversion de texte, consultez [Macros de Conversion de chaînes de MFC et ATL](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863).  
  
## <a name="example"></a>Exemple  
 Consultez la page [ATL et MFC Macros de Conversion de chaînes](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863) pour obtenir un exemple d’utilisation de ces macros de conversion de chaînes.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlconv.h  
  
##  <a name="cw2aex"></a>CW2AEX::CW2AEX  
 Constructeur.  
  
```
CW2AEX(LPCWSTR psz, UINT nCodePage) throw(...);  
CW2AEX(LPCWSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `psz`  
 La chaîne de texte à convertir.  
  
 `nCodePage`  
 La page de codes utilisée pour effectuer la conversion. Consultez la discussion de paramètre de page de code pour le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] fonction [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072) pour plus de détails.  
  
### <a name="remarks"></a>Remarques  
 Alloue de la mémoire tampon utilisée dans le processus de traduction.  
  
##  <a name="dtor"></a>CW2AEX :: ~ CW2AEX  
 Destructeur.  
  
```
~CW2AEX() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Libère la mémoire tampon allouée.  
  
##  <a name="m_psz"></a>CW2AEX::m_psz  
 Le membre de données qui stocke la chaîne source.  
  
```
LPSTR m_psz;
```  
  
##  <a name="m_szbuffer"></a>CW2AEX::m_szBuffer  
 La mémoire tampon statique, utilisé pour stocker la chaîne convertie.  
  
```
char m_szBuffer[t_nBufferLength];
```  
  
##  <a name="operator_lpstr"></a>CW2AEX::operator LPSTR  
 Opérateur de conversion.  
  
```  
operator LPSTR() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la chaîne de texte en tant que type **LPSTR.**  
  
## <a name="see-also"></a>Voir aussi  
 [CA2AEX (classe)](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX (classe)](../../atl/reference/ca2caex-class.md)   
 [CA2WEX (classe)](../../atl/reference/ca2wex-class.md)   
 [CW2CWEX (classe)](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX (classe)](../../atl/reference/cw2wex-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

