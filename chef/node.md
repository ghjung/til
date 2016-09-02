# Chef cookbook
## Node의 environment 확인
```ruby
if node.chef_environment == 'devel'
```

## Node가 Role을 가졌는지 확인
```ruby
if node.role?('ROLE_NAME')
```

## Node가 Recipe를 가졌는지 확인
```ruby
if node.recipes?('RECIPE_NAME')
```

