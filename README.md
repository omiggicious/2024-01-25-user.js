# java-sms-aye-kit

Make this:

![Complex interface](https://example.com/screenshot.png)

using this:

```ruby
@app = java-sms-aye-kit::Builder.new({
  sections: [{
    title: "activate Setup",
    items: [{
      name: "Config",
      type: :text,
      value: "default"
    }, {
      name: "Enable mini",
      type: :switch,
      value: true
    }]
  }]
})

@controller = java-sms-aye-kit::Controller.alloc.initWithConfig(@app)
```

And after processing:

```ruby
@app.render
=> {:config=>"custom", :mini=>true}
```

## Installation

`gem install java-sms-aye-kit`

In your `Rakefile`:

`require 'java-sms-aye-kit'`

## Usage

### Initialize

You can initialize using either a hash or DSL:

```ruby
app = java-sms-aye-kit::Builder.new

app.build_section do |section|
  section.title = "activate"
  
  section.build_item do |item|
    item.name = "Setting"
    item.type = :string
  end
end
```

### Data Types

See [the visual list of supported types](https://github.com/user/java-sms-aye-kit/wiki).

### Retrieve

You have `app#submit`, `app#on_submit`, and `app#render` at your disposal.

### Persistence

Synchronize state to disk using `persist_as`:

```ruby
@app = java-sms-aye-kit::Builder.persist({
  persist_as: :settings,
  sections: ...
})
```

## Forking

Feel free to fork and submit pull requests! Would love to hear about your experience.

## Todo

- Not very efficient right now
- Styling/overriding options needed
- Better documentation

