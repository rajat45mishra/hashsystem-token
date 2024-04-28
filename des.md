# UseCases Docs
```python 
# generating password hash and validating it
from hashsystem.hash.package import HashMachenism

# HashMachenism takes seeds as params for password salt
seeds={"seeds":[1,2,1,2]}
obj=HashMachenism(seeds)
dummypassword="testingtestpassword"
password_hash=obj.hasspass(dummypassword)
# output '$RMA-b@1c#2i(8a~0a~0b@1c#2i(8a~0a~0b@1c#2i(8a~0a~0b@1c#2i(8a~0a~0b@1c#2i(8a~0a~0b@1c#2i(8a~0a~0b@1c#2i(8a~0a~0b@1c#2i(8a~0a~0b@1c#2i(8a~0a~0'
# verifying pasword hash
obj.verify_password(password_hash) # returns True if verified

```
### Generating token and decoding it 
```python 
# imports for token generation
from hashsystem.hash.package import TokenGenerator
from datetime import datetime
# common vars
payload=dict(email="test@test.com",exp=datetime.now())
seeds=[1000,"%",20]
obj=TokenGenerator(payload,seeds)
token_hash=obj.get_token_pairs()

# decode token 

decoded=obj.get_formetted_token(token_hash['access_token'])

# please checkout documentaion for further implementation for token related features

```

