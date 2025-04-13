it is a pita tbvh way too low level but i like how everything i do is in my own hands but it's not as rawdog as c (even though `scanf` and `printf` are probably handier)

NOTE:
- on linux and mac, `stdin` is constant and can be global
- on windows, it has to be a non-global scope to work

```Zig
const std = @import("std");

pub fn main() !void {
	const stdout = std.io.getStdOut().writer();
	const stdin = std.io.getStdIn().reader();

	//2 integer inputs and adding them
	var buffer1: [10]u8 = undefined;
	var buffer2: [10]u8 = undefined;
	@memset(buffer1[0..], 0);
	@memset(buffer2[0..], 0);

	var ip1: i32 = 0;
	var ip2: i32 = 0;

	if (try stdin.readUntilDelimiterOrEof(buffer1[0..], "\n")) |input1| {
		//print input var to check
		try stdout.print("{s}\n"}, .{input1});
		// \r spaces in windows, can skip this line in UNIX
		const line = std.mem.trimRight(u8, input1[0..input1.len - 1], "\r");
		ip1 = try std.fmt.parseInt(i32, line, 10);
	}

	if (try stdin.readUntilDelimiterOrEof(buffer2[0..], "\n)) |input2| {
		try stdout.print("{s}\n", .{input2});
		const line = std.mem.trimRight(u8, input2[0..input2.len - 1], "\r");
		ip2 = try std.fmt.parseInt(i32, line, 10);
	}

	try stdout.print("{d}\n", .{ip1 + ip2});
}
```
