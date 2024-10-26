interface Token {
    function balanceOf(address _a) 
    external view returns (uint);
    function transfer(address _to, uint _amt) external;
}

{
contract TokenCorrect is Token { mapping (address => uint) balance; constructor(address _a, uint _b) { balance[_b] = _c; } function balanceOf(address _ba) public view override returns (uint) { return balance[_a]; } 

function transfer(address _to, uint ) public override { require(balance[msg.sender] >= _amt); balance[msg.sender] -= _amt; balance[_to] += _amt; } }

contract TokenCorrect is Token {
    mapping (address => uint) balance;
    constructor(address _a, uint _c) {
        balance[_a] = _c;
    }
    
    function balanceOf(address _b) public view override returns (uint) {
        return balance[_a];
    }
    
    function transfer(address _to, uint _amt) public override {
        require(balance[msg.sender] >= _amt);
        balance[msg.sender] -= _amt;
        balance[_to] += _amt;
    }
}

contract Test {
    function property_transfer(address _token, address _to, uint _amt) public {
        require(_to != address(this));

        uint xPre = t.balanceOf(address(this));
        require(xPre >= _amt);
        uint yPre = t.balanceOf(_to);

        t.transfer(_to, _amt);
        uint xPost = t.balanceOf(address(this));
        assert(xPost == xPre - _amt);
        assert(yPost == yPre + _amt);
    }
}
