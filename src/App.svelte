<script lang='ts'>
    import { Card, Col, Container, Input, Row } from 'sveltestrap';
    import { onMount } from 'svelte';
    import { GridMap } from './lib/pathfinding/GridMap';

    let gridMapCanvas: HTMLCanvasElement;
    let gridMap: GridMap;

    onMount(() => {
        const context = gridMapCanvas.getContext("2d");
    });
</script>

<Container>
    <Row class='my-4'>
        <Col xs='12'>
            <Card body>
                <Row>
                    <Col xs='6' lg='2'>
                        <Input type='select' name='select' id='algorithmSelect'>
                            <option value='dijkstra' selected>Dijkstra</option>
                            <option value='a-star'>A-Star</option>
                            <option value='ida-star'>IDA-Star</option>
                        </Input>
                    </Col>
                </Row>
            </Card>
        </Col>
    </Row>
    <Row>
        <Col>
            <Card body>
                <canvas bind:this={gridMapCanvas}></canvas>
            </Card>
        </Col>
    </Row>
</Container>

