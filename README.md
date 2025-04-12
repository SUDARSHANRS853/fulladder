// fulladder verilog code
module fa(a,b,c s,cout);
input a,b,c;
output s,cout;
wire w1,w2,w3;
xor x1(w1,a,b);
nand n1(w2,a,b);
nand n2(w3,w1,c);
xor x2(s,w1,c);
or o1(cout,w3,w2);
endmodule

// test bench 
module fa_tb;
reg a,b,c;
wire s,c;
fa dut(a,b,c,s,cout);
initial begin
$monitor(simtime=%0t,a=%b,b=%b,c=%b,s=%b,cout=%b",a,b,c,s,cout);
end
initial begin
$dumpfile("dump.vcd");
$dumpvars(0,a,b,c,s,cout);
end
endmodule


