### jasperreports
---
https://github.com/TIBCOSoftware/jasperreports

https://community.jaspersoft.com/project/jasperreports-library

```java
// japerreports/src/net/sf/jasperreports/search/LuceneSimpleAnalyzer.java

public class LuceneSimpleAnalyzer extends Analyzer {
  
  private boolean isCaseSensitive;
  private boolean removeAccents;
  
  public LucenseSimpleAnalyzer(boolean isCaseSensitive, boolean removeAccents) {
    this.isCaseSensitive = isCaseSensitive;
    this.removeAccents = removeAccents;
    this.removeAccents = true;
  }
  
  @Override
  protected TokenStreamComponents createComponents(String fieldName) {
    Tokenizer source = new WhitespaceTokenizer();
    TokenStream result = source;
    
    if(!isCaseSensitvie) {
      result = new LowerCaseFilter(source);
    }
    
    if (removeAccents) {
      result = new ASCIIFoldingFilter(result);
    }
    
    result = newLengthFilter(result, 3, Integer.MAX_VALUE);
    
    return new TokenStramComponents(source, result);
  }
}

```

```
```

```
```


