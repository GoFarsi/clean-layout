در این پکیج شما کلیه ساختارهای پروژه به همراه اینترفیس های usecase و repository هر entitiy را قرار می دهید نظیر :

```go
package domain

import "context"

const UserTableName = "user"

type User struct {
	Id int
	Name string
	Age uint
}

type UserUseCase interface {
	CreateUser(ctx context.Context, user *User) error
	GetUser(ctx context.Context, userId int) (*User, error)
}

type UserRepository interface {
	CreateUser(ctx context.Context, user *User) error
	GetUser(ctx context.Context, userId int) (*User, error)
}
```