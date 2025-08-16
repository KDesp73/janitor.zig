# janitor.zig

Clean up your `build.zig`

## Usage

```zig
const std = @import("std");
const Janitor = @import("janitor.zig");

pub fn build(b: *std.Build) void {
    var j = Janitor.init(b);
    j.exe("my_project");

    j.dep("dep1");
    j.dep("dep2");

    j.install();

    j.step(.run);
    j.step(.clean);

    j.customStep("custom-step", "This is a custom step", makeCustomStep);
}

fn makeCustomStep(step: *std.Build.Step, _: std.Build.Step.MakeOptions) anyerror!void {
    // Your code
}
```

## License

[MIT](./LICENSE)


