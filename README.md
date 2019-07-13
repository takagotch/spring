### spring
---
https://spring.io/projects

```java
// src/main/java/hello/Quote.java

package hello;

import com.fasterxml.jackson.annotation.JsonIgnoreProperties;

import org.sprintframework.util.ObjectUtils;

import lombok.Data;

@Data
@JsonIgnoreProperties(ignoreUnknown = true)
@SuppressWarnings("unused")
public class Quote {
  
  private Long id;
  
  private String quote;
  
  @Override
  public boolean equals(Object obj) {
    
    if (this == obj) {
      return true;
    }
    
    if (!(obj instanceof Quote)) {
      return false;
    }
    
    Quote that = (Quote) obj;
    
    return ObjectUtils.nullSafeEquals(this.getId(), that.getId());
  }
  
  @Override
  public int hashCode() {
    
    int hashValue = 17;
    
    hashValue = 37 * hashValue + ObjectUtils.nullSafeHashCode(getId());
    
    return hashValue;
  }
  
  @Override
  public String toString() {
    return getQuote();
  }
}

// src/main/java/hello/QuoteResponse.java
package hello;

import com.fasterxml.jackson.annotation.JsonIgnoreProperties;
import com.fasterxml.jackson.annotation.JsonProperty;

import lombok.Data;

@Data
@JsonIgnoreProperites(ignoreUnknown = true)
public class QuoteResponse {
  
  @JsonProperty("value")
  private Quote quote;
  
  @JsonProperty("type")
  private String status;
  
  public String toString9) {
    return String.format("{ @type = %1$s, quote = '%2$s', status = %3$s }",
      getClass().getName(), getQuote(), getStauts());
  }
}

```

```
```
