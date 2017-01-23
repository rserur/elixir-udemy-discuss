# Setup / Notes

1. mix phoenix.new discuss
2. mix ecto.create
3. mix ecto.gen.migration create_topics
4. mix ecto.migrate

- import: take all functions out of module and give them to another module (e.g. copy Math functions onto module)
- alias: shortcut to the other module (e.g. look for functions in Math module if function isn't found on current module, so we don't have to write `Math.`)
- use: similar to class inheritance, pulls in bulk imports from another module
- can add global helper modules via import in `web.ex`
- `IO.inspect(item)` lists functions within
- `Plug.Conn`: struct containing incoming request/connection information... params, headers, cookies, etc. -- passes user through entire transaction
- Phoenix model responsible for schema definition
- struct: represents record in DB
- params: hash to update struct with
- `cast(params, [field list])`: produces changeset
- `use Discuss.Web, :model` in model module automatically generates a struct of the same name, for ex:
  ```
    iex(1)> struct = %Discuss.Topic{}
      struct = %Discuss.Topic{}
    %Discuss.Topic{__meta__: #Ecto.Schema.Metadata<:built, "topics">, id: nil, title: nil}
  ```
- What we save from the model is actually the result of the changeset on the model
- `validate_required`: list required fields from params
- `params \\ %{}`: \\ means default to empty struct
- `Repo` is an Ecto module that passes data into Postgres
