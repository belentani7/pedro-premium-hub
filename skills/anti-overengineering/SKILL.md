---
name: anti-overengineering
description: Evita automáticamente el overengineering. El mejor código es el que no escribiste. Activa cuando detectes que estás creando abstracciones innecesarias, features no pedidas, o código excesivamente complejo.
---

# Anti-Overengineering - El código más simple que funciona

## Regla de Oro
**Si no puedes explicar por qué necesitas una abstracción en 10 palabras, no la necesitas.**

## Señales de Alerta (para)
```python
# ❌ SEÑAL: Abstracción prematura
class AbstractBaseFactorySingleton:
    def __init__(self):
        self.registry = {}
    
    def register(self, name, creator):
        self.registry[name] = creator
    
    def create(self, name):
        return self.registry[name]()

# ✅ SOLUCIÓN: Solo lo que necesitas
def create_user(data):
    return User(**data)
```

```python
# ❌ SEÑAL: Feature no pedida
def process_order(order, validate=True, notify=True, 
                  log=True, cache=True, retry=True, 
                  fallback=True, metrics=True):
    # 7 parámetros = overengineering
    pass

# ✅ SOLUCIÓN: Solo lo que piden
def process_order(order):
    # Hacer UNA cosa bien
    pass
```

```python
# ❌ SEÑAL: Nombre largo = concepto malo
class UserAuthenticationAuthorizationAndSessionManagementService:
    pass

# ✅ SOLUCIÓN: Nombres simples
class AuthService:
    pass
```

## Checklist Anti-Overengineering

### Antes de crear una abstracción:
- [ ] ¿Lo necesito AHORA, no "algún día"?
- [ ] ¿Lo usaré en más de 2 lugares?
- [ ] ¿Es más simple que la versión inline?
- [ ] ¿Puedo explicar por qué en 1 frase?

### Antes de agregar una feature:
- [ ] ¿El usuario la pidió?
- [ ] ¿Resuelve un problema REAL?
- [ ] ¿Es la solución más simple?
- [ ] ¿Se puede hacer en < 10 líneas?

### Antes de refactorizar:
- [ ] ¿El código actual funciona?
- [ ] ¿El refactor mejora algo medible?
- [ ] ¿El cambio es incremental, no big-bang?
- [ ] ¿Tengo tests que pasen después?

## Patrones de Overengineering

### 1. Abstract Factory innecesario
```python
# ❌ overkill para 2 implementaciones
class DatabaseFactory:
    def create(self, db_type):
        if db_type == 'postgres':
            return PostgresDB()
        elif db_type == 'mysql':
            return MySQLDB()

# ✅ simple
def get_db():
    return PostgresDB()  # Solo necesitas postgres
```

### 2. Configuración excesiva
```yaml
# ❌ 50 opciones para algo simple
server:
  host: localhost
  port: 3000
  timeout: 30
  retries: 3
  pool_size: 10
  max_overflow: 20
  # ... 45 opciones más

# ✅ solo lo necesario
server:
  port: 3000
```

### 3. Capas innecesarias
```python
# ❌ 4 capas para una query
class Repository:
    def find(self, id):
        return self.mapper.to_domain(
            self.dao.find(id)
        )

# ✅ 1 capa
def get_user(id):
    return db.query("SELECT * FROM users WHERE id = ?", id)
```

### 4. Validación excesiva
```python
# ❌ validar cada micro-detail
def process(data):
    validate_type(data)
    validate_length(data)
    validate_format(data)
    validate_range(data)
    validate_encoding(data)
    # ... 10 validaciones más

# ✅ validar lo crítico
def process(data):
    if not data:
        raise ValueError("data required")
    # Hacer el trabajo
```

## El Test del "Y luego qué?"
```python
def es_necesario(feature):
    """Pregunta: Y luego qué?"""
    resultado = feature.implementar()
    
    # Si la respuesta es "nada más", no era necesario
    if not resultado.tiene_consecuencias():
        return False
    
    # Si solo lo usarás una vez, hazlo inline
    if feature.usos == 1:
        return False
    
    # Si es más complejo que la versión simple, no lo hagas
    if feature.complejidad > feature.version_simple * 2:
        return False
    
    return True
```

## Regla YAGNI (You Aren't Gonna Need It)
```
1. No implementes funcionalidad por si la necesitas después
2. No crees abstracciones por si las necesitas después
3. No optimices por si es lento después
4. No documentes por si alguien lo pregunta después

HOY: implementa solo lo que sabes que necesitas
MAÑANA: refactoriza cuando lo necesites realmente
```
